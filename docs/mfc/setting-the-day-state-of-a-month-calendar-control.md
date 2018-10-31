---
title: 予定表コントロールの月の日付状態の設定 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- MCN_GETDAYSTATE
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], setting day state info
- MCN_GETDAYSTATE notification [MFC]
- month calendar controls [MFC], day state info
ms.assetid: 435d1b11-ec0e-4121-9e25-aaa6af812a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5e589f07d1c9c54c3acd2fa3ff6a0f346077f9b4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50053098"
---
# <a name="setting-the-day-state-of-a-month-calendar-control"></a>月間予定表コントロールの日付状態の設定

月間予定表コントロールの属性の 1 つは、月の日付ごとのコントロールの日付状態と呼ばれる情報を格納する機能です。 この情報は、現在表示されている月の特定の日付を強調するために使用されます。

> [!NOTE]
>  `CMonthCalCtrl`オブジェクトは、1 日の状態情報を表示する MCS_DAYSTATE スタイルをいる必要があります。

1 日の状態情報は、32 ビットのデータ型で表されます**月数**します。 各ビットを**月数**ビット フィールド (1 ~ 31) は、1 か月 1 日の状態を表します。 対応する日が表示されます、ビットが上にある場合は、太字で。それ以外の場合、太字で表示されます。

月間予定表コントロールの日付状態の設定の 2 つの方法があります: への呼び出しで明示的に[CMonthCalCtrl::SetDayState](../mfc/reference/cmonthcalctrl-class.md#setdaystate)または MCN_GETDAYSTATE 通知メッセージを処理します。

## <a name="handling-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE 通知メッセージの処理

MCN_GETDAYSTATE メッセージは、表示されるのか月以内の日の表示方法を決定するコントロールによって送信されます。

> [!NOTE]
>  コントロールが前月と翌月の表示中の月に関してはキャッシュするため、新しい月が選択されるたびにこの通知を受け取ります。

このメッセージを正しく処理するには、数か月に 1 日の状態情報が表示される数の要求の配列の初期化を確認する必要があります**月数**適切な値は、関連する構造体メンバーの初期化と構造体新しい情報。 詳細な手順では、次の手順では、あると想定する`CMonthCalCtrl`と呼ばれるオブジェクト*示します*と配列の**月数**オブジェクト、 *mdState*.

#### <a name="to-handle-the-mcngetdaystate-notification-message"></a>MCN_GETDAYSTATE 通知メッセージを処理するには

1. MCN_GETDAYSTATE メッセージの通知ハンドラーを追加する [プロパティ] ウィンドウを使用して、*示します*オブジェクト (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。

1. ハンドラーの本文には、次のコードを追加します。

   [!code-cpp[NVC_MFCControlLadenDialog#26](../mfc/codesnippet/cpp/setting-the-day-state-of-a-month-calendar-control_1.cpp)]

   例では、変換、 *pNMHDR* 、適切な型へのポインターが要求されている情報の数か月を決定し (`pDayState->cDayState`)。 月ごとの現在のビット フィールド (`pDayState->prgDayState[i]`)、し、必要とゼロに初期化されます (この例では、毎月 15 日) では日付が設定されます。

## <a name="see-also"></a>関連項目

[CMonthCalCtrl の使い方](../mfc/using-cmonthcalctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

