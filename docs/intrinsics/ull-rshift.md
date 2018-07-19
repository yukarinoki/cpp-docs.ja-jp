---
title: _ _ull_rshift |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ull_rshift
dev_langs:
- C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5248792d04efca518fc425a144c692cd88cf8d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333119"
---
# <a name="ullrshift"></a>__ull_rshift
**Microsoft 固有の仕様**  
  
 x64 では、2 番目のパラメーターで指定されたビット数だけ右に最初のパラメーターで指定した 64 ビット値を移動します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned __int64 __ull_rshift(   
   unsigned __int64 mask,    
   int nBit   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `mask`  
 右へシフトする 64 ビット整数値。  
  
 [入力] `nBit`  
 シフト、x86、32 剰余モジュロ x64 の 64 ビットの数。  
  
## <a name="return-value"></a>戻り値  
 マスクがずれる`nBit`ビットです。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__ull_rshift`|x86、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 2 番目のパラメーターが 31 on x86 (x64 では 63) よりも大きい場合は、シフトするビット数を調べてその数は 32 (x64 での 64) 剰余取得されます。 `ull`名前で示す`unsigned long long (unsigned __int64)`です。  
  
## <a name="example"></a>例  
  
```  
// ull_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ull_rshift)  
  
int main()  
{  
   unsigned __int64 mask = 0x100;  
   int nBit = 8;  
   mask = __ull_rshift(mask, nBit);  
   cout << hex << mask << endl;  
}  
```  
  
## <a name="output"></a>出力  
  
```  
1  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)