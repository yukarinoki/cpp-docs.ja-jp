---
title: _bittestandcomplement、_bittestandcomplement64 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _bittestandcomplement64
- _bittestandcomplement64_cpp
- _bittestandcomplement_cpp
- _bittestandcomplement
dev_langs:
- C++
helpviewer_keywords:
- btc instruction
- _bittestandcomplement intrinsic
- _bittestandcomplement64 intrinsic
ms.assetid: 53fa12dd-835e-4e5d-baec-a431c8678806
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 74040260149b6a22dcb673eb26f4561c4f324e61
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42544466"
---
# <a name="bittestandcomplement-bittestandcomplement64"></a>_bittestandcomplement、_bittestandcomplement64
**Microsoft 固有の仕様**  
  
 アドレス `b` のビット `a` を検査する命令を生成し、そのビットの現在値を返してビットに補数を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char _bittestandcomplement(  
   long *a,  
   long b  
);  
unsigned char _bittestandcomplement64(  
   __int64 *a,  
   __int64 b  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力、出力] `a`  
 検査するメモリへのポインター。  
  
 [入力] `b`  
 テストするビット位置。  
  
## <a name="return-value"></a>戻り値  
 指定した位置にあるビット。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_bittestandcomplement`|x86、ARM、x64|  
|`_bittestandcomplement64`|X64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 このルーチンは、組み込みとしてのみ使用できます。  
  
## <a name="example"></a>例  
  
```  
// bittestandcomplement.cpp  
// processor: x86, IPF, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_bittestandcomplement)  
#ifdef _M_AMD64  
#pragma intrinsic(_bittestandcomplement64)  
#endif  
  
int main()  
{  
   long i = 1;  
   __int64 i64 = 0x1I64;  
   unsigned char result;  
   printf("Initial value: %d\n", i);  
   printf("Testing bit 1\n");  
   result = _bittestandcomplement(&i, 1);  
   printf("Value changed to %d, Result: %d\n", i, result);  
#ifdef _M_AMD64  
   printf("Testing bit 0\n");  
   result = _bittestandcomplement64(&i64, 0);  
   printf("Value changed to %I64d, Result: %d\n", i64, result);  
#endif  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
Initial value: 1  
Testing bit 1  
Value changed to 3, Result: 0  
Testing bit 0  
Value changed to 0, Result: 1  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)