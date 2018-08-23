---
title: _disable |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _disable_cpp
- _disable
dev_langs:
- C++
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2748d0412c9ee0f7e7684d35a38f3c2b5d133754
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2018
ms.locfileid: "42541629"
---
# <a name="disable"></a>_disable
**Microsoft 固有の仕様**  
  
 割り込みを無効にします。  
  
## <a name="syntax"></a>構文  
  
```  
void _disable(void);  
```  
  
## <a name="requirements"></a>要件  
  
|組み込み|アーキテクチャ|  
|---------------|------------------|  
|`_disable`|x86、ARM、x64|  
  
 **ヘッダー ファイル** \<intrin.h >  
  
## <a name="remarks"></a>Remarks  
 `_disable` は、プロセッサに対して割り込みフラグをクリアするように指示します。 x86 システムでは、この関数は割り込みフラグのクリア (`cli`) 命令を生成します。  
  
 この関数はカーネル モードのみで使用できます。 ユーザー モードで使用した場合は、実行時に特権命令例外がスローされます。  
  
 ARM プラットフォームでは、このルーチンは組み込みとしてのみ使用できます。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)