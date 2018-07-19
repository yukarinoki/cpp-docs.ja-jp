---
title: ML の致命的でないエラー A2031 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2031
dev_langs:
- C++
helpviewer_keywords:
- A2031
ms.assetid: d5b11f58-4a00-42be-9062-8fa8728e6306
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4ab35776944604f3133254532d2631460c755983
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32057147"
---
# <a name="ml-nonfatal-error-a2031"></a>ML の致命的でないエラー A2031
**インデックスまたはベース レジスタである必要があります。**  
  
 メモリ式ではベースまたはインデックス レジスタでなかったレジスタを使用しようとしています。  
  
 たとえば、次の式では、このエラーが発生します。  
  
```  
[ax]  
[bl]  
```  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)