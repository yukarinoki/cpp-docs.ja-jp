---
description: '詳細情報: 月間予定表コントロールの作成'
title: 月間予定表コントロールの作成
ms.date: 11/04/2016
helpviewer_keywords:
- CMonthCalCtrl class [MFC], creating
- month calendar controls [MFC], creating
- month calendar controls [MFC]
ms.assetid: 185cc642-85e9-4365-8a4c-d90b75b010f7
ms.openlocfilehash: 98c707e16f05a8f5e4d3b42e3c9504f74e4aca29
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309525"
---
# <a name="creating-the-month-calendar-control"></a>月間予定表コントロールの作成

月間予定表コントロールの作成方法は、ダイアログボックスでコントロールを使用しているか、nondialog ウィンドウで作成したかによって異なります。

### <a name="to-use-cmonthcalctrl-directly-in-a-dialog-box"></a>ダイアログボックスで CMonthCalCtrl を直接使用するには

1. ダイアログエディターで、ダイアログテンプレートリソースに月間予定表コントロールを追加します。 コントロール ID を指定します。

1. 月間予定表コントロールの [プロパティ] ダイアログボックスを使用して、必要なスタイルを指定します。

1. [メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)を使用して、 [CMonthCalCtrl](reference/cmonthcalctrl-class.md)型のメンバー変数をコントロールプロパティに追加します。 このメンバーを使用して、メンバー関数を呼び出すことができ `CMonthCalCtrl` ます。

1. [クラスウィザード](reference/mfc-class-wizard.md)を使用すると、処理する必要がある月間予定表コントロールの通知メッセージのダイアログクラスのハンドラー関数をマップできます (「[関数へのメッセージのマッピング](reference/mapping-messages-to-functions.md)」を参照してください)。

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)で、オブジェクトの追加のスタイルを設定し `CMonthCalCtrl` ます。

### <a name="to-use-cmonthcalctrl-in-a-nondialog-window"></a>Nondialog ウィンドウで CMonthCalCtrl を使用するには

1. ビューまたはウィンドウクラスでコントロールを定義します。

1. コントロールの Create member 関数を呼び出します。これは、おそらく親ウィンドウの[OnCreate](reference/cwnd-class.md#oncreate) handler 関数 (コントロールをサブクラス化している場合) のように、 [OnInitialUpdate](reference/cview-class.md#oninitialupdate)で[作成](reference/cmonthcalctrl-class.md#create)します。 コントロールのスタイルを設定します。

## <a name="see-also"></a>関連項目

[CMonthCalCtrl の使い方](using-cmonthcalctrl.md)<br/>
[コントロール](controls-mfc.md)
