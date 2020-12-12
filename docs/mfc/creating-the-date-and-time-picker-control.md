---
description: '詳細情報: 日付と時刻の選択コントロールの作成'
title: 日時指定コントロールの作成
ms.date: 11/04/2016
helpviewer_keywords:
- DateTimePicker control [MFC], creating
- CDateTimeCtrl class [MFC], creating
ms.assetid: 764ec2fb-98cd-478b-a5f2-d63f0bb12279
ms.openlocfilehash: 0ead228e98fdcbcfe707fee88c175453808e7047
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309733"
---
# <a name="creating-the-date-and-time-picker-control"></a>日時指定コントロールの作成

日付と時刻の選択コントロールの作成方法は、ダイアログボックスでコントロールを使用するか、nondialog ウィンドウで作成するかによって異なります。

### <a name="to-use-cdatetimectrl-directly-in-a-dialog-box"></a>ダイアログボックスで Cdatetimectrl 使い方を直接使用するには

1. ダイアログエディターで、[日付と時刻の選択] コントロールをダイアログテンプレートリソースに追加します。 コントロール ID を指定します。

1. [日付と時刻の選択] コントロールの [プロパティ] ダイアログボックスを使用して、必要なスタイルを指定します。

1. [メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)を使用して、 [cdatetimectrl 使い方](reference/cdatetimectrl-class.md)型のメンバー変数をコントロールプロパティに追加します。 このメンバーを使用して、メンバー関数を呼び出すことができ `CDateTimeCtrl` ます。

1. [クラスウィザード](reference/mfc-class-wizard.md)を使用すると、処理する必要がある任意の日時指定コントロールの[通知](processing-notification-messages-in-date-and-time-picker-controls.md)メッセージのダイアログクラスのハンドラー関数をマップできます (「[関数へのメッセージのマッピング](reference/mapping-messages-to-functions.md)」を参照してください)。

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)で、オブジェクトの追加のスタイルを設定し `CDateTimeCtrl` ます。

### <a name="to-use-cdatetimectrl-in-a-nondialog-window"></a>Nondialog ウィンドウで Cdatetimectrl 使い方を使用するには

1. ビューまたはウィンドウクラスでコントロールを宣言します。

1. コントロールの Create member 関数を呼び出します。これは、おそらく親ウィンドウの[OnCreate](reference/cwnd-class.md#oncreate) handler 関数 (コントロールをサブクラス化している場合) のように、 [OnInitialUpdate](reference/cview-class.md#oninitialupdate)で[作成](reference/ctabctrl-class.md#create)します。 コントロールのスタイルを設定します。

## <a name="see-also"></a>関連項目

[CDateTimeCtrl の使い方](using-cdatetimectrl.md)<br/>
[コントロール](controls-mfc.md)
