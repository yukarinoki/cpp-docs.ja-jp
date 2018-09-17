---
title: _ _writeeflags |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __writeeflags
dev_langs:
- C++
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c01e10a77278f0a02658778ec178f0a4226eb36
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704861"
---
# <a name="writeeflags"></a>__writeeflags
指定した値をプログラムに書き込みますステータスと制御 (空文) を登録します。  
  
## <a name="syntax"></a>構文  
  
```  
void __writeeflags(unsigned Value);  
void __writeeflags(unsigned __int64 Value);  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|*値*|[in]立てるレジスタに書き込む値。 `Value`パラメーターは、32 ビット、32 ビット プラットフォームの時間の長いと 64 ビット、64 ビット プラットフォームの時間の長い。|  
  
## <a name="remarks"></a>Remarks  
 これらのルーチンは組み込みとしてのみ使用できます。  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`__writeeflags`|x86、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)   
 [__readeflags](../intrinsics/readeflags.md)