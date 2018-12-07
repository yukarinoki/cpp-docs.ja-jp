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
ms.openlocfilehash: 32e1b5954bc3f09f16c5516fc1c143dac716bc41
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693233"
---
# <a name="processing-tab-control-notification-messages"></a>タブ コントロールの通知メッセージの処理

ユーザーまたはボタン、タブ コントロールのタブをクリックすると、([CTabCtrl](../mfc/reference/ctabctrl-class.md))、親ウィンドウに通知メッセージを送信します。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーは、タブをクリックすると、それを表示する前に、ページ上のコントロール データの事前する可能性があります。

クラス ビューまたはダイアログのタブ コントロールから WM_NOTIFY メッセージの処理。 [プロパティ] ウィンドウを使用して作成する、 [OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify)ハンドラー関数を switch ステートメントが通知メッセージの処理に基づきます。 タブ コントロールを親ウィンドウに送信できる通知の一覧は、次を参照してください。、**通知**のセクション[タブ コントロールの参照](/windows/desktop/controls/tab-control-reference)Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[CTabCtrl の使い方](../mfc/using-ctabctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

