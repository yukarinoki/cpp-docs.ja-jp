---
title: フレームワークのメッセージとコマンド
ms.date: 11/04/2016
helpviewer_keywords:
- events [MFC], command routing in MFC
- event-driven programming [MFC]
- events [MFC], event-driven programming
- message-driven programming [MFC]
ms.assetid: d799ed8c-6a9f-4f05-be5d-29cb5bc6d185
ms.openlocfilehash: db529e2a22b45de3c6f6a659874bbaa941187217
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624292"
---
# <a name="messages-and-commands-in-the-framework"></a>フレームワークのメッセージとコマンド

Microsoft Windows 用に記述されたアプリケーションは "メッセージドリブン" です。 マウスのクリック、キー入力、ウィンドウの移動などのイベントに応答して、Windows は適切なウィンドウにメッセージを送信します。 フレームワークアプリケーションは、windows の他のアプリケーションと同様に Windows メッセージを処理します。 ただし、フレームワークには、メッセージの処理を容易にし、保守しやすく、より適切にカプセル化できるようにする拡張機能も用意されています。

次のトピックでは、メッセージとコマンドについて説明するために、記事ファミリの残りの部分で使用される主な用語を紹介します。

- [Messages (メッセージ)](messages.md)

- [メッセージハンドラー](message-handlers.md)

- [メッセージカテゴリ](message-categories.md)

- [Windows メッセージとコントロール通知メッセージ](message-categories.md)

- [コマンドメッセージ](message-categories.md)

- [メッセージマップ](mapping-messages.md)

- [ユーザー インターフェイス オブジェクトとコマンド ID](user-interface-objects-and-command-ids.md)

- [コマンドターゲット](command-targets.md)

## <a name="see-also"></a>関連項目

[メッセージの処理とマップ](message-handling-and-mapping.md)
