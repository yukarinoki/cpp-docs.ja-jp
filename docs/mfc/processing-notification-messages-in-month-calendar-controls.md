---
title: 月間予定表コントロールでの通知メッセージの処理
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], notifications
- CMonthCalCtrl class [MFC], day states
- month calendar controls [MFC], notification messages
- notifications [MFC], for CMonthCalCtrl
- notifications [MFC], month calendar control
ms.assetid: 607c3e90-0756-493b-9503-ce835a50c7ab
ms.openlocfilehash: fc0bb475a95450c281c92b500083c9502df50931
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346144"
---
# <a name="processing-notification-messages-in-month-calendar-controls"></a>月間予定表コントロールでの通知メッセージの処理

月間予定表コントロール (日付の選択や別の月を表示する)、コントロールを操作するユーザーと (`CMonthCalCtrl`) をその親ウィンドウに通知メッセージを送信します。 通常はビューまたはダイアログ オブジェクト。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーは、新しく表示する月を選択するときに強調する日付のセットを提供できます。

[プロパティ] ウィンドウを使用して、実装するメッセージの親クラスに通知ハンドラーを追加します。

次の一覧には、月間予定表コントロールから送信されたさまざまな通知がについて説明します。

- MCN_GETDAYSTATE 要求の情報については、日を太字で表示される必要があります。 この通知の処理方法の詳細については、次を参照してください。[月間予定表コントロールの日付状態の設定](../mfc/setting-the-day-state-of-a-month-calendar-control.md)します。

- MCN_SELCHANGE、選択した日付または日付の範囲が変更された親に通知します。

- MCN_SELECT 明示的な日付の選択範囲が作成されている親に通知します。

## <a name="see-also"></a>関連項目

[CMonthCalCtrl の使い方](../mfc/using-cmonthcalctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
