---
title: _ _readdr |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __readdr
dev_langs:
- C++
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d5cabbd1d779de4c6c081b57b8f241d9fa92f62
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709062"
---
# <a name="readdr"></a>__readdr
指定されたデバッグ レジスタの値を読み取ります。  
  
## <a name="syntax"></a>構文  
  
```  
unsigned         __readdr(unsigned int DebugRegister);  
unsigned __int64 __readdr(unsigned int DebugRegister);  
```  
  
#### <a name="parameters"></a>パラメーター  
*DebugRegister*<br/>
[in]デバッグを識別する 0 ~ 7 の定数を登録します。  
  
## <a name="return-value"></a>戻り値  
 指定されたデバッグ レジスタの値。  
  
## <a name="remarks"></a>Remarks  
 これらの組み込みはカーネル モードでのみ使用できますし、ルーチンは組み込みとしてのみ使用できます。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__readdr`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)