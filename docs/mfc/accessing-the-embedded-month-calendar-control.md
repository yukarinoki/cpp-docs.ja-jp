---
title: 予定表コントロールの埋め込みの月へのアクセス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a92660223c84c5f53bc848e72b03316602180d36
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430294"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>埋め込み月間予定表コントロールへのアクセス

埋め込み月間予定表コントロールのオブジェクトからアクセスできる、`CDateTimeCtrl`オブジェクトへの呼び出しで、 [GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)メンバー関数。

> [!NOTE]
>  埋め込み月間予定表コントロールが、日付と時刻の選択コントロールがない場合にのみ使用される、 **DTS_UPDOWN**一連のスタイルを設定します。

これは、埋め込まれたコントロールが表示される前に、特定の属性を変更する場合に便利です。 これを行うには、処理、 **DTN_DROPDOWN**通知では、月間予定表コントロールの取得 (を使用して[CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl))、修正を行うことです。 残念ながら、1 か月のカレンダー コントロールは不変ではありません。

言い換えると、ユーザーは、月間予定表コントロールの表示を要求、新しい月のカレンダー コントロールが作成されます (前に、 **DTN_DROPDOWN**通知)。 コントロールが破棄される (後に、 **DTN_CLOSEUP**通知)、ユーザーが消去されるときにします。 これは、埋め込まれたコントロールが消去されるときに、埋め込まれたコントロールが表示される前に、変更する任意の属性が失われることを意味します。

次の例のハンドラーを使用して、この手順を示して、 **DTN_DROPDOWN**通知します。 コードは、月間予定表コントロールの呼び出しでの背景色を変更[SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor)、灰色。 コードは次のとおりです。

[!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

前述のように、埋め込まれたコントロールが消去されるときに、月間予定表コントロールのプロパティに対するすべての変更は失われ、2 つの例外。 最初の例外では、月間予定表コントロールの色は、既に説明しました。 2 つ目の例外は、月間予定表コントロールで使用されるフォントです。 既定のフォントを変更するには、呼び出しを行う[CDateTimeCtrl::SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont)、既存のフォントのハンドルを渡します。 次の例では、(、`m_dtPicker`日付と時刻のコントロール オブジェクトは、) は 1 つの可能な方法を示します。

[!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

フォントが変更された後への呼び出しで`CDateTimeCtrl::SetMonthCalFont`、新しいフォントが格納され、次回に 1 か月カレンダーが表示されるときに使用します。

## <a name="see-also"></a>関連項目

[CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

