---
title: _rotl8、_rotl16 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _rotl8
- _rotl16
dev_langs:
- C++
helpviewer_keywords:
- _rotl8 intrinsic
- _rotl16 intrinsic
ms.assetid: 8c519ab6-aef9-4f07-a387-daee8408368f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 48a3cfe51f79f0d6068509a5e42693417524417d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="rotl8-rotl16"></a>_rotl8、_rotl16
**Microsoft 固有の仕様**  
  
 指定したビット位置の数だけ、最上位ビット (MSB) に向かって入力値を左に回転します。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned char _rotl8(   
   unsigned char value,   
   unsigned char shift   
);  
unsigned short _rotl16(   
   unsigned short value,   
   unsigned char shift   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 [入力] `value`  
 回転する値。  
  
 [入力] `shift`  
 回転するビット数。  
  
## <a name="return-value"></a>戻り値  
 回転後の値。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_rotl8`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_rotl16`|x86、ARM、[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>コメント  
 左シフト演算とは異なり、左回転を実行すると、上端からあふれた上位ビットは最下位ビット位置に移動します。  
  
## <a name="example"></a>例  
  
```  
// rotl.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_rotl8, _rotl16)  
  
int main()  
{  
    unsigned char c = 'A', c1, c2;  
  
    for (int i = 0; i < 8; i++)  
    {  
       printf_s("Rotating 0x%x left by %d bits gives 0x%x\n", c,  
               i, _rotl8(c, i));  
    }  
  
    unsigned short s = 0x12;  
    int nBit = 10;  
  
    printf_s("Rotating unsigned short 0x%x left by %d bits gives 0x%x\n",  
            s, nBit, _rotl16(s, nBit));  
}  
```  
  
```Output  
Rotating 0x41 left by 0 bits gives 0x41  
Rotating 0x41 left by 1 bits gives 0x82  
Rotating 0x41 left by 2 bits gives 0x5  
Rotating 0x41 left by 3 bits gives 0xa  
Rotating 0x41 left by 4 bits gives 0x14  
Rotating 0x41 left by 5 bits gives 0x28  
Rotating 0x41 left by 6 bits gives 0x50  
Rotating 0x41 left by 7 bits gives 0xa0  
Rotating unsigned short 0x12 left by 10 bits gives 0x4800  
```  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_rotr8、_rotr16](../intrinsics/rotr8-rotr16.md)   
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)