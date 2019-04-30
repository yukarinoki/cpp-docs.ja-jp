---
title: 日時指定コントロールの通知メッセージの処理
ms.date: 11/04/2016
f1_keywords:
- DTN_CLOSEUP
- DTN_DATETIMECHANGE
- DTN_DROPDOWN
helpviewer_keywords:
- DTN_DROPDOWN notification [MFC]
- DTN_DATETIMECHANGE notification [MFC]
- DTN_CLOSEUP notification [MFC]
- DateTimePicker control [MFC], handling notifications
- CDateTimeCtrl class [MFC], handling notifications
- DTN_FORMAT notification [MFC]
- DateTimePicker control [MFC]
ms.assetid: ffbe29ab-ff80-4609-89f7-260b404439c4
ms.openlocfilehash: ce84863744629d30248f94b94448d776177f9841
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339551"
---
# <a name="processing-notification-messages-in-date-and-time-picker-controls"></a>日時指定コントロールの通知メッセージの処理

日付と日時選択コントロールをコントロールにユーザーが操作すると (`CDateTimeCtrl`) をその親ウィンドウに通知メッセージを送信します。 通常はビューまたはダイアログ オブジェクト。 応答として何らかの操作を行う場合は、これらのメッセージを処理します。 たとえば、ユーザーは、埋め込み月間予定表コントロールを表示する日付と時刻のピッカーを起動したときに、DTN_DROPDOWN 通知が送信されます。

[プロパティ] ウィンドウを使用して、実装するメッセージの親クラスに通知ハンドラーを追加します。

次の一覧には、日付と時刻の選択コントロールから送信されたさまざまな通知について説明します。

- DTN_DROPDOWN 埋め込み月間予定表のコントロールの親が表示されることを通知します。 DTS_UPDOWN スタイルが設定されていない場合は、この通知は送信のみ。 この通知の詳細については、次を参照してください。[埋め込み月間予定表コントロールへのアクセス](../mfc/accessing-the-embedded-month-calendar-control.md)します。

- 埋め込み月間予定表のコントロールの親が閉じられます DTN_CLOSEUP に通知します。 DTS_UPDOWN スタイルが設定されていない場合は、この通知は送信のみ。

- DTN_DATETIMECHANGE に親コントロールの変更が発生したことを通知します。

- DTN_FORMAT コールバック フィールドに表示するために必要なテキストが親に通知します。 この通知とコールバック フィールドの詳細については、次を参照してください。[日付と時刻の選択コントロールでのコールバック フィールドを使用して](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)します。

- DTN_FORMATQUERY は、コールバック フィールドに表示される文字列の最大許容サイズを指定する親を要求します。 この通知を処理すると、常に、コントロールの表示のちらつきを軽減表示出力を適切に制御ができます。 この通知の詳細については、次を参照してください。[日付と時刻の選択コントロールでのコールバック フィールドを使用して](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md)します。

- DTN_USERSTRING に親のユーザーが、日付と時刻の選択コントロールの内容の編集を完了したことを通知します。 DTS_APPCANPARSE スタイルが設定されている場合、この通知は送信のみ。

- コールバック フィールドに、ユーザーが入力したとき DTN_WMKEYDOWN を親に通知します。 日付と時刻の選択コントロールでの非コールバック フィールドのサポートされている同じキーボード応答をエミュレートするには、この通知を処理します。 この通知の詳細については、次を参照してください。 [DTP コントロールでのコールバック フィールドのサポート](/windows/desktop/Controls/date-and-time-picker-controls)Windows SDK に含まれています。

## <a name="see-also"></a>関連項目

[CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
