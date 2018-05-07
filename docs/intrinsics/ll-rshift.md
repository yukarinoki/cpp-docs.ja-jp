---
title: _ _ll_rshift |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
dev_langs:
- C++
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4e086339c41f789323cb4aab386a96dae27a0eeb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="llrshift"></a>__ll_rshift
**Microsoft 固有の仕様**  
  
 2 番目のパラメーターで指定されたビット数だけ右に最初のパラメーターで指定した 64 ビット値を移動します。  
  
## <a name="syntax"></a>構文  
  
```  
__int64 __ll_rshift(  
   __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `Mask`  
 右へシフトする 64 ビット整数値。  
  
 [入力] `nBit`  
 モジュロ 64、x64 および x86 32 剰余、シフトするビット数。  
  
## <a name="return-value"></a>戻り値  
 マスクがずれる`nBit`ビットです。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__ll_rshift`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 2 番目のパラメーターが 64 on x64 (x86 32) よりも大きい場合は、その番号は、シフトするビット数を調べてモジュロ 64 (x86 32) 取得します。 `ll`プレフィックスは、の操作であることを示します`long long`、別の名前`__int64`、64 ビット符号付き整数型。  
  
## <a name="example"></a>例  
  
```  
// ll_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_rshift)  
  
int main()  
{  
   __int64 Mask = - 0x100;  
   int nBit = 4;  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
   Mask = __ll_rshift(Mask, nBit);  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
}  
```  
  
## <a name="output"></a>出力  
  
```  
ffffffffffffff00  
 - 100  
fffffffffffffff0  
 - 10  
```  
  
 **注**場合`_ull_rshift`されましたが、右にシフトした値の MSB が 0、ので、目的の結果が取得できていない場合は、負の値。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ組み込み関数](../intrinsics/compiler-intrinsics.md)   
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)