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
ms.openlocfilehash: 30e89c8d25d78477ed98bae0fd06a704e32d3906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349714"
---
# <a name="receiving-notification-from-common-controls"></a>コモン コントロールからの通知の受信
コモン コントロールは、コントロール、ユーザー入力のなどのイベントが発生した場合、親ウィンドウへ通知メッセージを送信する子ウィンドウです。  
  
 アプリケーションは、どのような操作、ユーザーが必要とするを決定するこれらの通知メッセージに依存します。 最も一般的なコントロールとして通知メッセージを送信する**WM_NOTIFY**メッセージ。 Windows のコントロールとしてのほとんどの通知メッセージを送信する**WM_COMMAND**メッセージ。 [CWnd::OnNotify](../mfc/reference/cwnd-class.md#onnotify)のハンドラーは、 **WM_NOTIFY**メッセージ。 同様に`CWnd::OnCommand`の実装`OnNotify`通知メッセージをディスパッチ`OnCmdMsg`メッセージ マップで処理するためです。 通知の処理のメッセージ マップ エントリが`ON_NOTIFY`です。 詳細については、次を参照してください。[テクニカル ノート 61: ON_NOTIFY メッセージと WM_NOTIFY メッセージ](../mfc/tn061-on-notify-and-wm-notify-messages.md)です。  
  
 派生クラスが「メッセージ リフレクション」を使用して、独自の通知メッセージを処理する代わりに、 詳細については、次を参照してください。[テクニカル ノート 62: Windows コントロールへのメッセージ リフレクション](../mfc/tn062-message-reflection-for-windows-controls.md)です。  
  
## <a name="retrieving-the-cursor-position-in-a-notification-message"></a>通知メッセージのカーソル位置を取得します。  
 場合によっては、共通のコントロールで特定の通知メッセージが受信され、カーソルの現在位置を決定すると便利です。 たとえば、これが役に立ちますコモン コントロールが受信すると、現在のカーソル位置を決定する、 **NM_RCLICK**通知メッセージです。  
  
 呼び出すことによってこれを実現する簡単な方法がある`CWnd::GetCurrentMessage`です。 ただし、このメソッドは、メッセージの送信時に、カーソルの位置を取得するだけにします。 カーソルが移動された可能性が呼び出す必要があります、メッセージが送信されたのでため**CWnd::GetCursorPos**を現在のカーソル位置を取得します。  
  
> [!NOTE]
>  `CWnd::GetCurrentMessage` メッセージ ハンドラー内でのみ呼び出す必要があります。  
  
 通知メッセージ ハンドラーの本体に次のコードを追加 (この例では**NM_RCLICK**)。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#4](../mfc/codesnippet/cpp/receiving-notification-from-common-controls_1.cpp)]  
  
 この時点では、マウスのカーソル位置は、`cursorPos`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [作成方法とコントロールの使用](../mfc/making-and-using-controls.md)   
 [コントロール](../mfc/controls-mfc.md)

