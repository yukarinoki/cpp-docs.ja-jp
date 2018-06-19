---
title: ML の致命的でないエラー A2008 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2008
dev_langs:
- C++
helpviewer_keywords:
- A2008
ms.assetid: ca24157f-c88a-4678-ae06-3bc3cd956001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 50f7329f698d23f875a29bc316067c39e8d1b8c1
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/28/2018
ms.locfileid: "32055220"
---
# <a name="ml-nonfatal-error-a2008"></a>ML の致命的でないエラー A2008
**構文エラー:**  
  
 現在の場所にトークンには、構文エラーが発生しました。  
  
 次のいずれかが発生した可能性があります。  
  
-   ドット プレフィックスを追加またはディレクティブから省略するとします。  
  
-   予約語 (など**C**または**サイズ**) 識別子として使用されました。  
  
-   現在のプロセッサまたはコプロセッサの選択を利用できなかった命令が使用されました。  
  
-   比較の実行時演算子 (など`==`)、関係演算子ではなく条件付きの assembly ステートメントで使用されていた (など[EQ](../../assembler/masm/operator-eq.md))。  
  
-   命令またはディレクティブが少なすぎますオペランドが指定されました。  
  
-   旧式のディレクティブが使用されました。  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)