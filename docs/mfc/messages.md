---
title: メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f25c9cc70cec598f975bbd242af83597311bdc7c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392256"
---
# <a name="messages"></a>メッセージ

メッセージ ループで、`Run`クラスのメンバー関数`CWinApp`を取得しますがさまざまなイベントによって生成されたメッセージをキューに登録します。 たとえば、ユーザーには、マウスがクリックすると、Windows は WM_LBUTTONDOWN マウスの左ボタンが押されたときに、マウスの左ボタンが離されたとき、WM_LBUTTONUP など、いくつかのマウス関連メッセージを送信します。 アプリケーション メッセージ ループのフレームワークの実装では、適切なウィンドウにメッセージをディスパッチします。

メッセージの重要なカテゴリが記載されて[メッセージ カテゴリ](../mfc/message-categories.md)します。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

