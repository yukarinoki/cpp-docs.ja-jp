---
description: '詳細情報: 月間予定表コントロールの日付状態の設定'
title: 月間予定表コントロールの日付状態の設定
ms.date: 11/04/2016
f1_keywords:
- MCN_GETDAYSTATE
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
ms.openlocfilehash: e7fc06516877c54aadaef715c33abd128bbd6994
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217212"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>月間予定表コントロールの日付状態の設定

月間予定表コントロールの属性の1つは、その月の各日に、コントロールの日付状態と呼ばれる情報を格納する機能です。 この情報は、現在表示されている月の特定の日付を強調するために使用されます。

> [!NOTE]
> `CMonthCalCtrl`日付状態情報を表示するには、オブジェクトに MCS_DAYSTATE スタイルが設定されている必要があります。

日状態情報は、32ビットのデータ型 **MONTHDAYSTATE** として表現されます。 **MONTHDAYSTATE** ビットフィールドの各ビット (1 ~ 31) は、月の1日の状態を表します。 ビットがオンの場合は、対応する日が太字で表示されます。それ以外の場合は、何も強調表示されません。

月間予定表コントロールの日の状態を設定するには、 [CMonthCalCtrl:: SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate) を明示的に呼び出す方法と MCN_GETDAYSTATE 通知メッセージを処理する方法の2つの方法があります。

## <a name="handling-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE 通知メッセージの処理

MCN_GETDAYSTATE メッセージはコントロールによって送信され、表示される月内の日数をどのように表示するかを決定します。

> [!NOTE]
> このコントロールは、表示されている月に対して前月と翌月をキャッシュするので、新しい月を選択するたびにこの通知を受け取ります。

このメッセージを適切に処理するには、要求されている月の状態情報の数を確認し、適切な値を使用して **MONTHDAYSTATE** 構造体の配列を初期化し、新しい情報で関連する構造体のメンバーを初期化します。 次の手順では、必要な手順について説明します `CMonthCalCtrl` 。 *m_monthcal* という名前のオブジェクトと、 **MONTHDAYSTATE** オブジェクトの *mdstate* の配列があることを前提としています。

#### <a name="to-handle-the-mcn_getdaystate-notification-message"></a>MCN_GETDAYSTATE 通知メッセージを処理するには

1. [クラスウィザード](reference/mfc-class-wizard.md)を使用して、MCN_GETDAYSTATE メッセージの通知ハンドラーを *m_monthcal* オブジェクトに追加します (「[関数へのメッセージのマッピング](../mfc/reference/mapping-messages-to-functions.md)」を参照してください)。

1. ハンドラーの本体に次のコードを追加します。

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   この例では、 *Pnmhdr* ポインターを適切な型に変換し、情報が要求される月数 () を決定し `pDayState->cDayState` ます。 月ごとに、現在のビットフィールド ( `pDayState->prgDayState[i]` ) が0に初期化され、必要な日付が設定されます (この場合は毎月15日)。

## <a name="see-also"></a>関連項目

[CMonthCalCtrl の使い方](../mfc/using-cmonthcalctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
