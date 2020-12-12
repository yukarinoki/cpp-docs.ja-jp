---
description: '詳細情報: コモンコントロールからの通知の受信'
title: コモン コントロールからの通知の受信
ms.date: 11/04/2016
helpviewer_keywords:
- OnNotify method [MFC]
- common controls [MFC], notifications
- ON_NOTIFY macro [MFC]
- controls [MFC], notifications
- receiving notifications from common controls
- notifications [MFC], common controls
- Windows common controls [MFC], notifications
- WM_NOTIFY message
ms.assetid: 50194592-d60d-44d0-8ab3-338a2a2c63e7
ms.openlocfilehash: a135dbc71447d31156ee4cfb223db410aad5218e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248555"
---
# <a name="receiving-notification-from-common-controls"></a>コモン コントロールからの通知の受信

コモンコントロールは、ユーザーからの入力などのイベントがコントロールで発生したときに、通知メッセージを親ウィンドウに送信する子ウィンドウです。

アプリケーションでは、これらの通知メッセージを使用して、ユーザーが実行する必要のあるアクションを決定します。 最も一般的なコントロールは、通知メッセージを WM_NOTIFY メッセージとして送信します。 Windows コントロールは、ほとんどの通知メッセージを WM_COMMAND メッセージとして送信します。 [CWnd:: OnNotify](../mfc/reference/cwnd-class.md#onnotify) は WM_NOTIFY メッセージのハンドラーです。 と同様に `CWnd::OnCommand` 、の実装は、 `OnNotify` `OnCmdMsg` メッセージマップでの処理のために通知メッセージをにディスパッチします。 通知を処理するためのメッセージマップエントリが ON_NOTIFY ます。 詳細については、「 [テクニカルノート 61: ON_NOTIFY および WM_NOTIFY メッセージ](../mfc/tn061-on-notify-and-wm-notify-messages.md)」を参照してください。

または、派生クラスが "メッセージリフレクション" を使用して独自の通知メッセージを処理することもできます。 詳細については、「 [テクニカルノート 62: Windows コントロールのメッセージリフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)」を参照してください。

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>通知メッセージ内のカーソル位置を取得する

場合によっては、コモンコントロールが特定の通知メッセージを受信したときにカーソルの現在位置を特定すると便利です。 たとえば、コモンコントロールが NM_RCLICK 通知メッセージを受信したときに、現在のカーソルの位置を確認すると便利です。

を呼び出すことによってこれを実現する簡単な方法があり `CWnd::GetCurrentMessage` ます。 ただし、このメソッドは、メッセージが送信された時点のカーソル位置だけを取得します。 カーソルはメッセージの送信後に移動された可能性があるため、 `CWnd::GetCursorPos` 現在のカーソル位置を取得するにはを呼び出す必要があります。

> [!NOTE]
> `CWnd::GetCurrentMessage` は、メッセージハンドラー内でのみ呼び出す必要があります。

通知メッセージハンドラーの本文に次のコードを追加します (この例では NM_RCLICK)。

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

この時点で、マウスカーソルの位置はオブジェクトに格納され `cursorPos` ます。

## <a name="see-also"></a>関連項目

[コントロールの作成と使用](../mfc/making-and-using-controls.md)<br/>
[コントロール](../mfc/controls-mfc.md)
