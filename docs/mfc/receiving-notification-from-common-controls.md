---
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
ms.openlocfilehash: 9205facb5ec4e2491308020d9667a27ab8deb96b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371780"
---
# <a name="receiving-notification-from-common-controls"></a>コモン コントロールからの通知の受信

コモン コントロールは、ユーザーからの入力などのイベントがコントロールで発生したときに、親ウィンドウに通知メッセージを送信する子ウィンドウです。

アプリケーションは、ユーザーが実行するアクションを決定するために、これらの通知メッセージに依存します。 一般的なコントロールでは、通知メッセージWM_NOTIFYメッセージとして送信されます。 Windows コントロールは、ほとんどの通知メッセージをWM_COMMANDメッセージとして送信します。 [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify)は、WM_NOTIFY メッセージのハンドラーです。 と同様`CWnd::OnCommand`に、の実装`OnNotify`は、メッセージ マップで`OnCmdMsg`処理するために通知メッセージを ディスパッチします。 通知を処理するためのメッセージ マップ エントリがON_NOTIFY。 詳細については、テクニカル[ノート 61: ON_NOTIFYおよびWM_NOTIFYメッセージ](../mfc/tn061-on-notify-and-wm-notify-messages.md)を参照してください。

または、派生クラスは、"メッセージ リフレクション" を使用して独自の通知メッセージを処理できます。 詳細については、「[テクニカル ノート 62: Windows コントロールのメッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)」を参照してください。

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>通知メッセージ内のカーソル位置の取得

コモン コントロールが特定の通知メッセージを受信した場合に、カーソルの現在位置を判断すると便利な場合があります。 たとえば、コモン コントロールがNM_RCLICK通知メッセージを受信したときに、現在のカーソル位置を確認すると便利です。

これを行うには、 を呼び出す`CWnd::GetCurrentMessage`簡単な方法があります。 ただし、このメソッドは、メッセージが送信された時点でのカーソル位置のみを取得します。 メッセージの送信後にカーソルが移動されている可能性があるため、現在のカーソル`CWnd::GetCursorPos`位置を取得するために呼び出す必要があります。

> [!NOTE]
> `CWnd::GetCurrentMessage`メッセージ ハンドラ内でのみ呼び出す必要があります。

通知メッセージ ハンドラーの本文に次のコードを追加します (この例では、NM_RCLICK)。

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

この時点で、マウス カーソルの位置がオブジェクトに`cursorPos`格納されます。

## <a name="see-also"></a>関連項目

[コントロールの作成方法と使い方](../mfc/making-and-using-controls.md)<br/>
[コントロール](../mfc/controls-mfc.md)
