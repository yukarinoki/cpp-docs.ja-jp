---
title: コモン コントロールから通知を受信 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 80fefde054ed411dcb30836b2b89cef89cc54e64
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928795"
---
# <a name="receiving-notification-from-common-controls"></a>コモン コントロールからの通知の受信
コモン コントロールは、コントロール、ユーザー入力のなどのイベントが発生した場合、親ウィンドウへ通知メッセージを送信する子ウィンドウです。  
  
 アプリケーションは、どのような操作、ユーザーが必要とするを決定するこれらの通知メッセージに依存します。 最も一般的なコントロールは、通知メッセージを WM_NOTIFY メッセージとして送信します。 Windows のコントロールは、WM_COMMAND メッセージとしてほとんどの通知メッセージを送信します。 [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify) WM_NOTIFY メッセージのハンドラーがします。 同様に`CWnd::OnCommand`の実装`OnNotify`通知メッセージをディスパッチ`OnCmdMsg`メッセージ マップで処理するためです。 通知の処理のメッセージ マップ エントリは、ON_NOTIFY がします。 詳細については、次を参照してください。[テクニカル ノート 61: ON_NOTIFY メッセージと WM_NOTIFY メッセージ](../mfc/tn061-on-notify-and-wm-notify-messages.md)です。  
  
 派生クラスが「メッセージ リフレクション」を使用して、独自の通知メッセージを処理する代わりに、 詳細については、次を参照してください。[テクニカル ノート 62: Windows コントロールへのメッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)です。  
  
## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>通知メッセージのカーソル位置を取得します。  
 場合によっては、共通のコントロールで特定の通知メッセージが受信され、カーソルの現在位置を決定すると便利です。 たとえば、共通コントロール NM_RCLICK 通知メッセージを受け取るときに、現在のカーソル位置を確認すると役立つでしょう。  
  
 呼び出すことによってこれを実現する簡単な方法がある`CWnd::GetCurrentMessage`です。 ただし、このメソッドは、メッセージの送信時に、カーソルの位置を取得するだけにします。 カーソルが移動された可能性が呼び出す必要があります、メッセージが送信されたのでため`CWnd::GetCursorPos`を現在のカーソル位置を取得します。  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage` メッセージ ハンドラー内でのみ呼び出す必要があります。  
  
 (この例では、NM_RCLICK) では、通知メッセージ ハンドラーの本体に次のコードを追加します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]  
  
 この時点では、マウスのカーソル位置は、`cursorPos`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [作成方法とコントロールの使用](../mfc/making-and-using-controls.md)   
 [コントロール](../mfc/controls-mfc.md)

