---
title: 埋め込み月間予定表コントロールへのアクセス
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], accessing month calendar
- CDateTimeCtrl class [MFC], accessing embedded control
- month calendar controls [MFC], embedded in date/time picker
- CMonthCalCtrl class [MFC], changing the font
- month calendar controls [MFC], changing the font
- DateTimePicker control [MFC]
ms.assetid: 355e97ed-cf81-4df3-a2f8-9ddbbde93227
ms.openlocfilehash: 69270cc5663406f2c5d38ffccdbd35f39298a3d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354179"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>埋め込み月間予定表コントロールへのアクセス

埋め込まれた月間予定表コントロール オブジェクトは`CDateTimeCtrl`[、GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)メンバー関数の呼び出しを使用して、オブジェクトからアクセスできます。

> [!NOTE]
> 埋め込み月間予定表コントロールは、日付と時刻の選択コントロールに**DTS_UPDOWN**スタイルが設定されていない場合にのみ使用されます。

これは、埋め込みコントロールを表示する前に特定の属性を変更する場合に便利です。 これを実現するには **、DTN_DROPDOWN**通知を処理し、月間予定表コントロールを取得し[(CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)を使用して)、変更を加えます。 残念ながら、月間予定表コントロールは永続的ではありません。

つまり、ユーザーが月間予定表コントロールの表示を要求すると、新しい月間予定表コントロールが作成されます **(DTN_DROPDOWN**通知の前)。 ユーザーがコントロールを破棄すると、コントロールは破棄されます **(DTN_CLOSEUP**通知後)。 つまり、埋め込みコントロールが表示される前に変更した属性は、埋め込みコントロールが閉じられたときに失われます。

次の例は **、DTN_DROPDOWN**通知のハンドラーを使用して、この手順を示しています。 コードは、月の予定表コントロールの背景色を変更し[、SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor)を呼び出して灰色にします。 コードは次のとおりです。

[!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

前に述べたように、埋め込みコントロールが閉じられたときに、2 つの例外を除いて、月間予定表コントロールのプロパティに対するすべての変更が失われます。 最初の例外は、月間予定表コントロールの色は既に説明されています。 2 つ目の例外は、月間予定表コントロールで使用されるフォントです。 既定のフォントを変更するには、既存のフォントのハンドルを渡して[呼](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont)び出します。 次の例 (`m_dtPicker`日付と時刻のコントロール オブジェクト) は、1 つの可能なメソッドを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

フォントが変更されると、 を`CDateTimeCtrl::SetMonthCalFont`呼び出すと、新しいフォントが保存され、次に月のカレンダーが表示される際に使用されます。

## <a name="see-also"></a>関連項目

[CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
