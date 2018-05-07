---
title: _mm_stream_ss |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_stream_ss
dev_langs:
- C++
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5058ac6c415f155b6a7cab712002d4769983d1f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="mmstreamss"></a>_mm_stream_ss  
  
**Microsoft 固有の仕様**  
  
 キャッシュを汚染せずに、32 ビットのデータをメモリ位置に書き込みます。  
  
## <a name="syntax"></a>構文  
  
```  
void _mm_stream_ss(  
   float * Dest,  
   __m128 Source  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
 [出力] `Dest`  
 ソース データが書き込まれる場所へのポインター。  
  
 [入力] `Source`  
 128 ビットの数値を含む、 `float` 32 ビットの下に書き込まれる値.  
  
## <a name="return-value"></a>戻り値  
  
 なし。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_mm_stream_ss`|SSE4a|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
  
この組み込みを生成、`movntss`命令します。 この命令のハードウェア サポートを確認するのには、呼び出し、`__cpuid`で組み込み`InfoType=0x80000001`のビット 6 をチェックし、`CPUInfo[2] (ECX)`です。 このビットは、それ以外の場合、命令がサポートされている場合は 1 および 0 です。  
  
使用するコードを実行する場合、`_mm_stream_ss`サポートしていないハードウェアの組み込み、`movntss`命令、結果は予測できません。  
  
## <a name="example"></a>例  
  
```cpp  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128 vals;  
    float f[4];  
  
    f[0] = -1.;  
    f[1] = -2.;  
    f[2] = -3.;  
    f[3] = -4.;  
    vals.m128_f32[0] = 0.;  
    vals.m128_f32[1] = 1.;  
    vals.m128_f32[2] = 2.;  
    vals.m128_f32[3] = 3.;  
    _mm_stream_ss(&f[3], vals);  
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;  
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;  
}  
```  
  
```Output  
f[0] = -1, f[1] = -2  
f[2] = -3, f[3] = 3  
```  
  
**Microsoft 固有の仕様はここまで**  

高度なマイクロ デバイス, Inc. によって copyright 2007All rights reserved. 高度なマイクロ デバイス, Inc. のアクセス許可を持つ再現  
  
## <a name="see-also"></a>関連項目  
 [_mm_stream_sd](../intrinsics/mm-stream-sd.md)   
 [_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)   
 [_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)   
 [_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)