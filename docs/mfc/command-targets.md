---
title: コマンドのターゲット |Microsoft Docs
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
ms.openlocfilehash: 408f63b80ff30a7ebdc51e5becb1dd97bb062852
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404229"
---
# <a name="command-targets"></a>コマンド ターゲット

図[フレームワークにおけるコマンド](../mfc/user-interface-objects-and-command-ids.md)メニュー項目と、オブジェクトがクリックされたときに、結果として得られるコマンドを実行するフレームワークから呼び出されるハンドラー関数などのユーザー インターフェイス オブジェクト間の接続を示しています。

Windows では、メッセージのハンドラーが呼び出され、ウィンドウに直接コマンド メッセージではないメッセージを送信します。 フレームワークが複数の候補のオブジェクトにコマンドをルーティングするただし、-「コマンド ターゲット」と呼ばれる、うちの 1 つ通常コマンドのハンドラーを呼び出します。 ハンドラー関数の動作のコマンドと標準の Windows メッセージの両方に対して同じ方法で説明したように、呼び出されるメカニズムが異なり、[フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)します。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

