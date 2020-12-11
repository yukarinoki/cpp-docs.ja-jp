---
description: '詳細情報: タブコントロールの通知メッセージの処理'
title: タブ コントロールの通知メッセージの処理
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tab controls
- CTabCtrl class [MFC], processing notifications
- notifications [MFC], processing in CTabCtrl
- processing notifications [MFC]
- tab controls [MFC], processing notifications
ms.assetid: 758ccb7a-9e73-48f8-9073-23f7cb09918c
ms.openlocfilehash: f5d81437b566143e2fc7cb1e0f275c0f9e9993de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154722"
---
# <a name="processing-tab-control-notification-messages"></a>タブ コントロールの通知メッセージの処理

ユーザーがタブまたはボタンをクリックすると、タブコントロール ([CTabCtrl](../mfc/reference/ctabctrl-class.md)) によって通知メッセージが親ウィンドウに送信されます。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーがタブをクリックしたときに、表示する前にページにコントロールデータを事前設定することができます。

ビューまたはダイアログクラスのタブコントロールから WM_NOTIFY メッセージを処理します。 [クラスウィザード](reference/mfc-class-wizard.md)を使用して、処理されている通知メッセージに基づいた switch ステートメントを含む[OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify) handler 関数を作成します。 タブコントロールが親ウィンドウに送信できる通知の一覧については、Windows SDK の「[タブコントロールリファレンス](/windows/win32/controls/tab-control-reference)」の「**通知**」セクションを参照してください。

## <a name="see-also"></a>関連項目

[CTabCtrl の使い方](../mfc/using-ctabctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
