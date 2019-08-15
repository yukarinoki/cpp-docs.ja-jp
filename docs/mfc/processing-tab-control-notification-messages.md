---
title: タブ コントロールの通知メッセージの処理
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
ms.openlocfilehash: 97abde8285a3baf307df79fd97d4f9a379c8f58f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507830"
---
# <a name="processing-tab-control-notification-messages"></a>タブ コントロールの通知メッセージの処理

ユーザーがタブまたはボタンをクリックすると、タブコントロール ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) によって通知メッセージが親ウィンドウに送信されます。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーがタブをクリックしたときに、表示する前にページにコントロールデータを事前設定することができます。

ビューまたはダイアログクラスのタブコントロールから、WM_NOTIFY メッセージを処理します。 プロパティウィンドウを使用して、処理されている通知メッセージに基づいて switch ステートメントを含む[OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) handler 関数を作成します。 タブコントロールが親ウィンドウに送信できる通知の一覧については、Windows SDK の「[タブコントロールリファレンス](/windows/win32/controls/tab-control-reference)」の「**通知**」セクションを参照してください。

## <a name="see-also"></a>関連項目

[CTabCtrl の使い方](../mfc/using-ctabctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
