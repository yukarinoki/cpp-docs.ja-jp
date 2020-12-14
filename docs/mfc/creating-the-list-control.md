---
description: 詳細については、「リストコントロールの作成」を参照してください。
title: リスト コントロールの作成
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: 5be1a9ce7a2cd8279d576dfc41e44c810c433515
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309577"
---
# <a name="creating-the-list-control"></a>リスト コントロールの作成

リストコントロール ([CListCtrl](reference/clistctrl-class.md)) の作成方法は、コントロールを直接使用しているか、代わりに [CListView](reference/clistview-class.md) クラスを使用しているかによって異なります。 を使用する場合、 `CListView` フレームワークはドキュメント/ビュー作成シーケンスの一部としてビューを構築します。 リストビューを作成すると、リストコントロールも作成されます (2 つは同じです)。 コントロールは、ビューの [OnCreate](reference/cwnd-class.md#oncreate) handler 関数に作成されます。 この場合、コントロールは、 [Getlistctrl](reference/clistview-class.md#getlistctrl)の呼び出しを使用して、項目を追加する準備ができています。

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>ダイアログボックスで CListCtrl を直接使用するには

1. ダイアログエディターで、ダイアログテンプレートリソースにリストコントロールを追加します。 コントロール ID を指定します。

1. [メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)を使用して、コントロールのプロパティを持つ型のメンバー変数を追加し `CListCtrl` ます。 このメンバーを使用して、メンバー関数を呼び出すことができ `CListCtrl` ます。

1. [クラスウィザード](reference/mfc-class-wizard.md)を使用すると、処理する必要のあるリストコントロールの通知メッセージのダイアログクラスのハンドラー関数をマップできます (「[関数へのメッセージのマッピング](reference/mapping-messages-to-functions.md)」を参照してください)。

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)で、のスタイルを設定し `CListCtrl` ます。 「 [リストコントロールスタイルの変更](changing-list-control-styles.md)」を参照してください。 これにより、コントロールで取得する "表示" の種類が決まります。ただし、後でビューを変更することはできます。

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>Nondialog ウィンドウで CListCtrl を使用するには

1. ビューまたはウィンドウクラスでコントロールを定義します。

1. コントロールの Create member 関数を呼び出します。これは、おそらく親ウィンドウの[OnCreate](reference/cwnd-class.md#oncreate) handler 関数 (コントロールをサブクラス化している場合) のように、 [OnInitialUpdate](reference/cview-class.md#oninitialupdate)で[作成](reference/clistctrl-class.md#create)します。 コントロールのスタイルを設定します。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](using-clistctrl.md)<br/>
[コントロール](controls-mfc.md)
