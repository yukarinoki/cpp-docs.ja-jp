---
title: 月間予定表コントロールの日付状態の設定
ms.date: 11/04/2016
f1_keywords:
- MCN_GETDAYSTATE
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
ms.openlocfilehash: 9892f2d853687787dd76428fc9bc95f3a4f74565
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365429"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>月間予定表コントロールの日付状態の設定

月間予定表コントロールの属性の 1 つは、各日の情報を格納する機能です。 この情報は、現在表示されている月の特定の日付を強調するために使用されます。

> [!NOTE]
> オブジェクト`CMonthCalCtrl`には、日の状態情報を表示するMCS_DAYSTATEスタイルが必要です。

日の状態情報は、32 ビットのデータ型**MONTHDAYSTATE**として表されます。 **MONTHDAYSTATE**ビット フィールド (1 ~ 31) の各ビットは、1 か月の 1 日の状態を表します。 ビットがオンの場合、対応する日は太字で表示されます。それ以外の場合は、強調なしで表示されます。

月の予定表コントロールの日の状態を設定するには[、CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate)の呼び出しを明示的に使用するか、MCN_GETDAYSTATE通知メッセージを処理する 2 つの方法があります。

## <a name="handling-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE通知メッセージの処理

MCN_GETDAYSTATE メッセージは、表示される月内の日数を表示する方法を決定するために、コントロールによって送信されます。

> [!NOTE]
> コントロールは、表示される月に関して前月と次の月をキャッシュするため、新しい月が選択されるたびにこの通知を受け取ります。

このメッセージを適切に処理するには、何か月の日の状態情報が要求されているかを判別し、正しい値を使用して**MONTHDAYSTATE**構造体の配列を初期化し、関連する構造体メンバーを新しい情報で初期化する必要があります。 以下の手順は、必要な手順を詳述し *、m_monthcal*と呼`CMonthCalCtrl`ばれるオブジェクトと**MONTHDAYSTATE**オブジェクトの配列*mdState*があることを前提としています。

#### <a name="to-handle-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE通知メッセージを処理するには

1. クラス[ウィザード](reference/mfc-class-wizard.md)を使用して *、MCN_GETDAYSTATE*メッセージの通知ハンドラーをm_monthcal オブジェクトに追加します (「[関数へのメッセージのマッピング](../mfc/reference/mapping-messages-to-functions.md)」を参照)。

1. ハンドラーの本体に、次のコードを追加します。

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   この例では *、pNMHDR*ポインタを適切な型に変換し、要求されている情報の数を決定します`pDayState->cDayState`( ) 。 各月に対して、現在のビット`pDayState->prgDayState[i]`フィールド ( ) がゼロに初期化され、必要な日付 (この場合は各月の 15 日) が設定されます。

## <a name="see-also"></a>関連項目

[CMonthCalCtrl の使い方](../mfc/using-cmonthcalctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
