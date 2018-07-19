---
title: ML の致命的でないエラー A2085 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2085
dev_langs:
- C++
helpviewer_keywords:
- A2085
ms.assetid: c2fef415-a32b-4249-896c-6d981fc6e327
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82f0a014810679f0b48f79198b1335240f5cd6a8
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32054277"
---
# <a name="ml-nonfatal-error-a2085"></a>ML の致命的でないエラー A2085
**命令またはレジスタが CPU の現在のモードでは許可されません。**  
  
 命令、レジスタ、または現在のプロセッサ モードの無効なキーワードを使用しようとしました。  
  
 たとえば、32 ビット レジスタが必要な[.386](../../assembler/masm/dot-386.md)またはそれ以降。 CR0 特権モードが必要などの制御レジスタ[.386P](../../assembler/masm/dot-386p.md)またはそれ以降。 このエラーが生成されます、 **NEAR32**、 **FAR32**、および**フラット**を必要とするキーワードです **。386**またはそれ以降。  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)