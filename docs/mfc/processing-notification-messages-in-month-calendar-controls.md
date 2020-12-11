---
description: '詳細情報: 月間予定表コントロールでの通知メッセージの処理'
title: 月間予定表コントロールでの通知メッセージの処理
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
ms.openlocfilehash: 4c527bd2c950277d36164ec14c7c714d82d2c812
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154787"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>月間予定表コントロールでの通知メッセージの処理

ユーザーが月間予定表コントロールを操作する (日付を選択するか、別の月を表示する) と、コントロール ( `CMonthCalCtrl` ) は親ウィンドウ (通常はビューまたはダイアログオブジェクト) に通知メッセージを送信します。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーが表示する新しい月を選択すると、強調表示する日付のセットを指定できます。

[クラスウィザード](reference/mfc-class-wizard.md)を使用して、実装するメッセージの親クラスに通知ハンドラーを追加します。

次の一覧では、月間予定表コントロールによって送信されるさまざまな通知について説明します。

- MCN_GETDAYSTATE は、どの日を太字で表示するかに関する情報を要求します。 この通知を処理する方法については、「 [月間予定表コントロールの日付状態の設定](../mfc/setting-the-day-state-of-a-month-calendar-control.md)」を参照してください。

- MCN_SELCHANGE は、選択した日付または日付の範囲が変更されたことを親に通知します。

- MCN_SELECT は、明示的な日付の選択が行われたことを親に通知します。

## <a name="see-also"></a>関連項目

[CMonthCalCtrl の使い方](../mfc/using-cmonthcalctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
