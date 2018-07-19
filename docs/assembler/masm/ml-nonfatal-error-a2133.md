---
title: ML の致命的でないエラー A2133 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2133
dev_langs:
- C++
helpviewer_keywords:
- A2133
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f240ed6f2e8330017e56334dfcc41be478537c7b
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32056208"
---
# <a name="ml-nonfatal-error-a2133"></a>ML の致命的でないエラー A2133
**レジスタ値の呼び出しによって上書きされます。**  
  
 レジスタは、プロシージャに引数として渡されたが、コードによって生成[INVOKE](../../assembler/masm/invoke.md)他の引数を渡す、レジスタの内容を破棄します。  
  
 AX、AL、AH、EAX、DX、DL、DH、および EDX レジスタは、アセンブラーによってデータの変換を実行するために使用可能性があります。  
  
 別のレジスタを使用します。  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)