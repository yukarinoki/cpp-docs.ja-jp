---
title: _mm_extract_si64、_mm_extracti_si64 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_extracti_si64
- _mm_extract_si64
dev_langs:
- C++
helpviewer_keywords:
- extrq instruction
- _mm_extracti_si64 intrinsic
- _mm_extract_si64 intrinsic
ms.assetid: 459fdd72-cc54-4ee5-bbd5-d2c6067a88e7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8ba4986abf097a5827d3db7f93dbbd0a9640862
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33331455"
---
# <a name="mmextractsi64-mmextractisi64"></a>_mm_extract_si64、_mm_extracti_si64
**Microsoft 固有の仕様**  
  
 生成、`extrq`最初の引数の下位 64 ビットから指定したビットを抽出する命令です。  
  
## <a name="syntax"></a>構文  
  
```  
__m128i _mm_extract_si64(  
   __m128i Source,  
   __m128i Descriptor  
);  
__m128i _mm_extracti_si64(  
   __m128i Source,  
   int Length,  
   int Index  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `Source`  
 入力データの下位 64 ビットでは、128 ビット フィールドです。  
  
 [in]  `Descriptor`  
 抽出するビット フィールドを説明する 128 ビット フィールドです。  
  
 [in]  `Length`  
 抽出するフィールドの長さを指定する整数。  
  
 [in]  `Index`  
 抽出するフィールドのインデックスを指定する整数  
  
## <a name="return-value"></a>戻り値  
 その最下位のビット単位で抽出されたフィールドでは、128 ビット フィールドです。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_mm_extract_si64`|SSE4a|  
|`_mm_extracti_si64`|SSE4a|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 この組み込みを生成、`extrq`からのビットを抽出する命令`Source`です。この 2 つのバージョンがある組み込み:`_mm_extracti_si64`即時のバージョンと`_mm_extract_si64`緊急であります。  各バージョンがから抽出`Source`その長さと、その最下位ビットのインデックスで定義されたビット フィールドです。 長さとインデックスの値は取得されます mod 64、-1 および 127 の両方が 63 として解釈されるためです。 (縮小) のインデックスと (縮小) フィールドの長さの合計を 64 を超える場合、結果は未定義です。 フィールド長に 0 の値は、64 として解釈されます。 場合、フィールドの長さとビットのインデックスの両方で 0 ビット 63:0`Source`抽出されます。 フィールドの長さが 0 ですが、ビットのインデックスは 0 以外、結果は未定義です。  
  
 _Mm_extract_si64 への呼び出しで、 `Descriptor` bits 13:8 および bits 5:0 で抽出するデータのフィールド長、インデックスが含まれています.  
  
 呼び出す場合`_mm_extracti_si64`コンパイラは、整数定数である判断できない引数を指定して、コンパイラは XMM レジスタにそれらの値をパックするコードを生成 (`Descriptor`) を呼び出す`_mm_extract_si64`です。  
  
 ハードウェア サポートの決定を`extrq`命令、呼び出し、`__cpuid`で組み込み`InfoType=0x80000001`のビット 6 をチェックし、`CPUInfo[2] (ECX)`です。 このビットはある命令がサポートされている場合は 1 と 0 それ以外の場合。 サポートしていないこの固有のハードウェアを使用するコードを実行するかどうか、`extrq`命令、結果は予測できません。  
  
## <a name="example"></a>例  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source, descriptor, result1, result2, result3;  
  
int  
main()  
{  
    source.ui64[0] =     0xfedcba9876543210ll;  
    descriptor.ui64[0] = 0x0000000000000b1bll;  
  
    result1.m = _mm_extract_si64 (source.m, descriptor.m);  
    result2.m = _mm_extracti_si64(source.m, 27, 11);  
    result3.ui64[0] = (source.ui64[0] >> 11) & 0x7ffffff;  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
}  
```  
  
```Output  
result1 = 0x30eca86  
result2 = 0x30eca86  
result3 = 0x30eca86  
```  
  
**Microsoft 固有の仕様はここまで**  
 高度なマイクロ デバイス, Inc. によって copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. のアクセス許可を持つ再現  
  
## <a name="see-also"></a>関連項目  
 [_mm_insert_si64、_mm_inserti_si64](../intrinsics/mm-insert-si64-mm-inserti-si64.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)