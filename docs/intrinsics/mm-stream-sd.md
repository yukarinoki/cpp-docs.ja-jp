---
title: _mm_stream_sd |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_stream_sd
dev_langs:
- C++
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e8a65066ad19b78319867782255d70da8d5b721
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mmstreamsd"></a>_mm_stream_sd
**Microsoft 固有の仕様**  
  
 キャッシュを汚染せずに、64 ビットのデータをメモリ位置に書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [出力] `Dest`  
 ソース データの書き込み先の場所へのポインター。  
  
 [入力] `Source`  
 128 ビットの値を含む、`double`値の 64 ビットの下で記述する.  
  
## <a name="return-value"></a>戻り値  
 なし。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_mm_stream_sd`|SSE4a|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 この組み込みを生成、`movntsd`命令します。 この命令のハードウェア サポートを確認するのには、呼び出し、`__cpuid`で組み込み`InfoType=0x80000001`のビット 6 をチェックし、`CPUInfo[2] (ECX)`です。 ハードウェアがサポートする場合、この命令と 0 それ以外の場合、このビットは 1 です。  
  
 使用するコードを実行する場合、`_mm_stream_sd`サポートしていないハードウェアの組み込み、`movntsd`命令、結果は予測できません。  
  
## <a name="example"></a>例  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128d vals;  
    double d[2];  
  
    d[0] = -1.;  
    d[1] = -2.;  
    vals.m128d_f64[0] = 0.;  
    vals.m128d_f64[1] = 1.;  
    _mm_stream_sd(&d[1], vals);  
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;  
}  
  
```  
  
```Output  
d[0] = -1, d[1] = 1  
```  
  
**Microsoft 固有の仕様はここまで**  
 高度なマイクロ デバイス, Inc. によって copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. のアクセス許可を持つ再現  
  
## <a name="see-also"></a>関連項目  
 [_mm_stream_ss](../intrinsics/mm-stream-ss.md)   
 [_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)   
 [_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)