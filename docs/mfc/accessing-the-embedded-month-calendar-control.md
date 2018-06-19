---
title: 予定表コントロールの埋め込み月間にアクセスする |Microsoft ドキュメント
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
ms.openlocfilehash: cfbc9ce7b99efc1f8d99f5735c16c252ff613c59
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332128"
---
# <a name="accessing-the-embedded-month-calendar-control"></a>埋め込み月間予定表コントロールへのアクセス
埋め込み月間予定表コントロール オブジェクトからアクセスできる、`CDateTimeCtrl`オブジェクトへの呼び出しを[GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl)メンバー関数。  
  
> [!NOTE]
>  埋め込み月間予定表コントロールが、日付と時刻の選択コントロールがない場合にのみ使用される、 **DTS_UPDOWN**セットのスタイルを設定します。  
  
 これは、埋め込まれたコントロールが表示される前に、特定の属性を変更する場合に便利です。 これを実現する、処理、 **DTN_DROPDOWN**通知には、月間予定表コントロールの取得 (を使用して[CDateTimeCtrl::GetMonthCalCtrl](../mfc/reference/cdatetimectrl-class.md#getmonthcalctrl))、修正を行うことです。 残念ながら、月間予定表コントロールは、永続的ではなくです。  
  
 つまり、ユーザーは、月間予定表コントロールの表示を要求、新しい月のカレンダー コントロールが作成 (前に、 **DTN_DROPDOWN**通知)。 コントロールが破棄されます (後、 **DTN_CLOSEUP**通知)、ユーザーが破棄されたときにします。 これは、埋め込まれたコントロールが破棄されたときに変更すると、埋め込まれたコントロールが表示される前にすべての属性が失われることを意味します。  
  
 次の例では、ハンドラーを使用して、この手順の**DTN_DROPDOWN**通知します。 コードは、月間予定表コントロールの呼び出しの背景色を変更[SetMonthCalColor](../mfc/reference/cdatetimectrl-class.md#setmonthcalcolor)、グレー表示にします。 コードは次のとおりです。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#5](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_1.cpp)]  
  
 既に説明したように、月間予定表コントロールのプロパティに対するすべての変更の値は埋め込まれたコントロールが破棄されたときに、2 つの例外を除き、失われます。 最初の例外では、月間予定表コントロールの色は既に説明しました。 2 つ目の例外は、月間予定表コントロールで使用されるフォントです。 既定のフォントを変更するには、呼び出しを行う[CDateTimeCtrl::SetMonthCalFont](../mfc/reference/cdatetimectrl-class.md#setmonthcalfont)、既存のフォントのハンドルを渡すことです。 次の例 (ここで`m_dtPicker`日付と時刻のコントロール オブジェクトは、) 可能な 1 つの方法を示します。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#6](../mfc/codesnippet/cpp/accessing-the-embedded-month-calendar-control_2.cpp)]  
  
 フォントが変更された後を呼び出して`CDateTimeCtrl::SetMonthCalFont`、新しいフォントが格納され、次回、月間予定表が表示されることを使用します。  
  
## <a name="see-also"></a>関連項目  
 [CDateTimeCtrl の使い方](../mfc/using-cdatetimectrl.md)   
 [コントロール](../mfc/controls-mfc.md)

