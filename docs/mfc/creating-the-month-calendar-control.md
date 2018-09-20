---
title: 予定表コントロールの 1 か月の作成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0fadc3b56d0aa64068071ee7230ed125c6af925
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410872"
---
# <a name="creating-the-month-calendar-control"></a>月間予定表コントロールの作成

月間予定表コントロールの作成方法は、ダイアログ ボックスで、コントロールの使用または以外のウィンドウで作成するかどうかによって異なります。

### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>CMonthCalCtrl をダイアログ ボックスで直接使用するには

1. ダイアログ エディターでダイアログ テンプレート リソースを 1 か月のカレンダー コントロールを追加します。 そのコントロールの ID を指定します

1. 月間予定表コントロールのプロパティ ダイアログ ボックスを使用して、必要に応じてスタイルを指定します。

1. 使用して、[メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)型のメンバー変数を追加する[CMonthCalCtrl](../mfc/reference/cmonthcalctrl-class.md)コントロール プロパティにします。 このメンバーを使用するには、呼び出しと`CMonthCalCtrl`メンバー関数。

1. 使用ダイアログ クラスのハンドラー関数をマップする任意の 1 か月カレンダー コントロールの通知メッセージの [プロパティ] ウィンドウを処理する必要があります (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)、追加のスタイルを設定、`CMonthCalCtrl`オブジェクト。

### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>以外のウィンドウで関数を使用するには

1. ビューまたはウィンドウのクラスでは、コントロールを定義します。

1. コントロールの呼び出し[作成](../mfc/reference/cmonthcalctrl-class.md#create)メンバー関数は、おそらくで[OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)、親ウィンドウの可能性がありますの早期[OnCreate](../mfc/reference/cwnd-class.md#oncreate)いる場合、ハンドラー関数コントロールをサブクラス)。 コントロールのスタイルを設定します。

## <a name="see-also"></a>関連項目

[CMonthCalCtrl の使い方](../mfc/using-cmonthcalctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

