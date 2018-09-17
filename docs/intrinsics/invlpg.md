---
title: _ _invlpg |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __invlpg
- __invlpg_cpp
dev_langs:
- C++
helpviewer_keywords:
- invlpg instruction
- __invlpg intrinsic
ms.assetid: 3fb3633f-d9b7-4ec0-9e7f-a7f2fa8ed794
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ada416217be672da8f93c777b0b2a6e12684711
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45703028"
---
# <a name="invlpg"></a>__invlpg
**Microsoft 固有の仕様**  
  
 X86 が生成されます`invlpg`、命令が指すメモリに関連付けられているページの変換ルック アサイド バッファ (TLB) を無効になります`Address`します。  
  
## <a name="syntax"></a>構文  
  
```  
void __invlpg(  
   void* Address  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
*アドレス*<br/>
[in]64 ビットのアドレス。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__invlpg`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 組み込みの`__invlpg`特権命令を生成し、0 の特権レベル (CPL) でのカーネル モードでのみ使用します。  
  
 このルーチンは、組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)