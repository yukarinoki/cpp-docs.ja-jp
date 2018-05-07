---
title: コマンド ターゲット |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1cbcfa1042a8430c704bad93e4bc0ce5655b5921
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="command-targets"></a>コマンド ターゲット
図[フレームワークにおけるコマンド](../mfc/user-interface-objects-and-command-ids.md)メニュー項目とその結果、コマンド オブジェクトがクリックされたときに実行するためにフレームワークから呼び出されるハンドラー関数などのユーザー インターフェイス オブジェクト間の接続を示しています。  
  
 Windows では、メッセージのハンドラーが呼び出されますウィンドウに直接コマンド メッセージではないメッセージを送信します。 ただし、フレームワークは候補オブジェクトの数にコマンドを送ります —「コマンド ターゲット」と呼ばれる — うちの 1 つ通常コマンドのハンドラーを呼び出します。 ハンドラー関数のコマンドと標準の Windows メッセージの両方で同様の動作で説明したように、呼び出されるメカニズムが異なる場合、[フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)です。  
  
## <a name="see-also"></a>関連項目  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

