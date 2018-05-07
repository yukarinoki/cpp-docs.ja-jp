---
title: _mm_insert_si64、_mm_inserti_si64 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_inserti_si64
- _mm_insert_si64
dev_langs:
- C++
helpviewer_keywords:
- insertq instruction
- _mm_insert_si64 intrinsic
- _mm_inserti_si64 intrinsic
ms.assetid: 897a4b36-8b08-4b00-a18f-7850f5732d7d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72597007922e78ab9b83687cb5b80bd6ecef7d01
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mminsertsi64-mminsertisi64"></a>_mm_insert_si64、_mm_inserti_si64
**Microsoft 固有の仕様**  
  
 生成、`insertq`ビットを 2 番目のオペランドから最初のオペランドに挿入する命令です。  
  
## <a name="syntax"></a>構文  
  
```  
__m128i _mm_insert_si64(  
   __m128i Source1,  
   __m128i Source2  
);  
__m128i _mm_inserti_si64(  
   __m128i Source1,  
   __m128i Source2  
   int Length,  
   int Index  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `Source1`  
 入力データの下位 64 ビット フィールドの挿入先では、128 ビット フィールドです。  
  
 [in]  `Source2`  
 その下位ビットに挿入するデータでは、128 ビット フィールドです。  `_mm_insert_si64`もフィールド記述子の上位ビットに含まれています。  
  
 [in]  `Length`  
 整数の定数を挿入するフィールドの長さを指定します。  
  
 [in]  `Index`  
 データを挿入するフィールドの最下位ビットのインデックスを指定する整数の定数です。  
  
## <a name="return-value"></a>戻り値  
 128 ビット フィールドの下位 64 ビットの元の下位 64 ビットを含む`Source1`、指定されたビット フィールドの下位ビットを置き換えて`Source2`です。 戻り値の上位 64 ビットは、定義されていません。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_mm_insert_si64`|SSE4a|  
|`_mm_inserti_si64`|SSE4a|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 この組み込みを生成、`insertq`からのビットを挿入する命令`Source2`に`Source1`です。 この 2 つのバージョンがある組み込み: `_mm_inserti_si64`、即時のバージョンと`_mm_insert_si64`緊急であります。  各バージョンでは、Source2 から指定された長さのビット フィールドを抽出し、Source1 に挿入します。  抽出されたビットは、Source2 の最下位ビットです。  これらのビットが挿入されるフィールド Source1 は、長さと、その最下位ビットのインデックスによって定義されます。  長さとインデックスの値は取得されます mod 64、-1 および 127 の両方が 63 として解釈されるためです。 (縮小) のビットのインデックスと (縮小) フィールドの長さの合計を 64 を超える場合、結果は未定義です。 フィールド長に 0 の値は、64 として解釈されます。  フィールドの長さとビットのインデックスがゼロの両方のビット 63:0 の場合は`Source2`に挿入された`Source1`です。  フィールドの長さが 0 ですが、ビットのインデックスは 0 以外、結果は未定義です。  
  
 _Mm_insert_si64 への呼び出しでは、フィールドの長さは Source2 および bits 69:64 内のインデックスのビット 77:72 に含まれます。  
  
 呼び出す場合`_mm_inserti_si64`XMM レジスタにそれらの値をパックしてを呼び出すコードを生成するコンパイラ、コンパイラは、整数定数である判断できない引数で`_mm_insert_si64`です。  
  
 ハードウェア サポートの決定を`insertq`命令呼び出し、`__cpuid`で組み込み`InfoType=0x80000001`のビット 6 をチェックし、`CPUInfo[2] (ECX)`です。 このビットはある命令がサポートされている場合は 1 と 0 それ以外の場合。 かどうかはコードを実行するを使用するこの組み込みをサポートしていないハードウェア、`insertq`命令、結果は予測できません。  
  
## <a name="example"></a>例  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
union {  
    __m128i m;  
    unsigned __int64 ui64[2];  
} source1, source2, source3, result1, result2, result3;  
  
int  
main()  
{  
  
    __int64 mask;  
  
    source1.ui64[0] = 0xffffffffffffffffll;  
    source2.ui64[0] = 0xfedcba9876543210ll;  
    source2.ui64[1] = 0xc10;  
    source3.ui64[0] = source2.ui64[0];  
  
    result1.m = _mm_insert_si64 (source1.m, source2.m);  
    result2.m = _mm_inserti_si64(source1.m, source3.m, 16, 12);  
    mask = 0xffff << 12;  
    mask = ~mask;  
    result3.ui64[0] = (source1.ui64[0] & mask) |  
                      ((source2.ui64[0] & 0xffff) << 12);  
  
    cout << hex << "result1 = 0x" << result1.ui64[0] << endl;  
    cout << "result2 = 0x" << result2.ui64[0] << endl;  
    cout << "result3 = 0x" << result3.ui64[0] << endl;  
  
}  
```  
  
```Output  
result1 = 0xfffffffff3210fff  
result2 = 0xfffffffff3210fff  
result3 = 0xfffffffff3210fff  
```  
  
**Microsoft 固有の仕様はここまで**  
 高度なマイクロ デバイス, Inc. によって copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. のアクセス許可を持つ再現  
  
## <a name="see-also"></a>関連項目  
 [_mm_extract_si64、_mm_extracti_si64](../intrinsics/mm-extract-si64-mm-extracti-si64.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)