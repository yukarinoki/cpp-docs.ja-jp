---
title: コモン コントロールからの通知の受信
ms.date: 11/04/2016
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
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
ms.openlocfilehash: fb923374866aa8348f9b895c9b97915817564883
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287428"
---
# <a name="receiving-notification-from-common-controls"></a>コモン コントロールからの通知の受信

一般的なコントロールは、コントロールで、ユーザーからの入力などのイベントが発生したときに、親ウィンドウに通知メッセージを送信する子ウィンドウです。

アプリケーションは、これらの通知メッセージを確認してどのような操作、ユーザーが実行することに依存します。 最も一般的なコントロールは、通知メッセージを WM_NOTIFY メッセージとして送信します。 Windows のコントロールは、WM_COMMAND メッセージとして、ほとんどの通知メッセージを送信します。 [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) WM_NOTIFY メッセージのハンドラーします。 同様`CWnd::OnCommand`の実装`OnNotify`通知メッセージをディスパッチ`OnCmdMsg`メッセージ マップで処理します。 通知を処理するためのメッセージ マップ エントリは、ON_NOTIFY です。 詳細については、次を参照してください。[テクニカル ノート 61。ON_NOTIFY メッセージと WM_NOTIFY メッセージ](../mfc/tn061-on-notify-and-wm-notify-messages.md)します。

派生クラスが「メッセージ リフレクション」を使用して、独自の通知メッセージを処理する代わりに、 詳細については、次を参照してください。[テクニカル ノート 62。メッセージの Windows コントロールへのリフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)します。

## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>通知メッセージのカーソル位置を取得します。

場合によっては、一般的なコントロールで特定の通知メッセージが受信され、カーソルの現在位置を決定すると便利です。 たとえば、一般的なコントロール NM_RCLICK 通知メッセージを受け取るときに、現在のカーソル位置を確認すると役立つでしょう。

呼び出すことによってこれを実現する簡単な方法がある`CWnd::GetCurrentMessage`します。 ただし、このメソッドは、メッセージの送信時に、カーソルの位置を取得するだけにします。 カーソルが移動された可能性が呼び出す必要があります、メッセージの送信以降ため`CWnd::GetCursorPos`を現在のカーソル位置を取得します。

> [!NOTE]
>  `CWnd::GetCurrentMessage` メッセージ ハンドラー内でのみ呼び出す必要があります。

(この例では、NM_RCLICK) では、通知メッセージ ハンドラーの本体に次のコードを追加します。

[!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]

マウス カーソルの位置が格納されているこの時点で、`cursorPos`オブジェクト。

## <a name="see-also"></a>関連項目

[コントロールの作成方法と使い方](../mfc/making-and-using-controls.md)<br/>
[コントロール](../mfc/controls-mfc.md)
