---
title: ML の致命的でないエラー A2096 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2096
dev_langs:
- C++
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e5d07afa864c9f6f4214de953aa9e03fe0e7e4f
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32053673"
---
# <a name="ml-nonfatal-error-a2096"></a>ML の致命的でないエラー A2096
**セグメント、グループ、またはセグメント レジスタが必要です。**  
  
 セグメントまたはグループが必要でしたが、見つかりませんでした。  
  
 次のいずれかが発生しました。  
  
-   セグメントに指定した左オペランドに演算子がオーバーライド (**:**) セグメント レジスタ (CS、DS、SS、ES、FS、または GS)、グループ名、セグメント名、またはセグメント式ありませんでした。  
  
-   [想定](../../assembler/masm/assume.md)ディレクティブは、セグメント レジスタに有効なセグメントのアドレス、セグメント レジスタ、グループ、または特別なを指定しました**フラット**グループ。  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)