---
description: '詳細情報: 埋め込み月間予定表コントロールへのアクセス'
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
ms.openlocfilehash: 35c715cdd84bd7921883db530c8cf36e8e5cf07e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169451"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>埋め込み月間予定表コントロールへのアクセス

埋め込み月間予定表コントロールオブジェクトには、 `CDateTimeCtrl` [GetMonthCalCtrl](reference/cdatetimectrl-class.md#getmonthcalctrl) メンバー関数を呼び出すことによって、オブジェクトからアクセスできます。

> [!NOTE]
> 埋め込み月間予定表コントロールは、日付と時刻の選択コントロールに **DTS_UPDOWN** スタイルが設定されていない場合にのみ使用されます。

これは、埋め込みコントロールを表示する前に特定の属性を変更する場合に便利です。 これを実現するには、 **DTN_DROPDOWN** 通知を処理し、月間予定表コントロール ( [Cdatetimectrl 使い方:: GetMonthCalCtrl](reference/cdatetimectrl-class.md#getmonthcalctrl)を使用) を取得して、変更を行います。 残念ながら、月間予定表コントロールは永続的ではありません。

つまり、ユーザーが月間予定表コントロールの表示を要求すると、 **DTN_DROPDOWN** 通知の前に新しい月間予定表コントロールが作成されます。 ユーザーによって破棄されると、コントロールが ( **DTN_CLOSEUP** 通知の後に) 破棄されます。 これは、埋め込まれたコントロールが表示される前に変更したすべての属性が、埋め込みコントロールが破棄されると失われることを意味します。

次の例では、 **DTN_DROPDOWN** 通知にハンドラーを使用して、この手順を示します。 このコードは、 [SetMonthCalColor](reference/cdatetimectrl-class.md#setmonthcalcolor)の呼び出しをグレーにして、月間予定表コントロールの背景色を変更します。 コードは次のとおりです。

[!code-cpp[NVC_MFCControlLadenDialog#5](codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]

前述のように、月間予定表コントロールのプロパティに対する変更はすべて失われます。ただし、埋め込みコントロールが破棄されると、2つの例外があります。 最初の例外である、月間予定表コントロールの色は既に説明されています。 2つ目の例外は、月間予定表コントロールで使用されるフォントです。 既定のフォントを変更するには、 [cdatetimectrl 使い方:: SetMonthCalFont](reference/cdatetimectrl-class.md#setmonthcalfont)を呼び出して、既存のフォントのハンドルを渡します。 次の例 ( `m_dtPicker` は日付と時刻の制御オブジェクト) は、考えられる1つの方法を示しています。

[!code-cpp[NVC_MFCControlLadenDialog#6](codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]

フォントが変更され、を呼び出すと、 `CDateTimeCtrl::SetMonthCalFont` 新しいフォントが保存され、次に月間予定表が表示されるときに使用されます。

## <a name="see-also"></a>関連項目

[CDateTimeCtrl の使い方](using-cdatetimectrl.md)<br/>
[コントロール](controls-mfc.md)
