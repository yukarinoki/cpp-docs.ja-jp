---
title: リスト コントロールの作成
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], creating control
- list controls [MFC]
ms.assetid: a4cb1729-31b6-4d2b-a44b-367474848a39
ms.openlocfilehash: 7b2cb47699339dd413dc1bfae7623069da56e7a4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303650"
---
# <a name="creating-the-list-control"></a>リスト コントロールの作成

一覧を制御する方法 ([CListCtrl](../mfc/reference/clistctrl-class.md)) が作成されるクラスを使用してまたはコントロールを直接使用するしているかどうかによって異なります[CListView](../mfc/reference/clistview-class.md)代わりにします。 使用する場合`CListView`フレームワークのドキュメント/ビュー作成シーケンスの一部として、ビューを構築します。 リスト ビューを作成するには、(2 つは同じもの) もリスト コントロールが作成されます。 ビューのコントロールが作成された[OnCreate](../mfc/reference/cwnd-class.md#oncreate)ハンドラー関数。 この場合、コントロールが呼び出しを使用しての項目を追加するための準備ができて[GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl)します。

### <a name="to-use-clistctrl-directly-in-a-dialog-box"></a>ダイアログ ボックスで直接 CListCtrl を使用するには

1. ダイアログ エディターでダイアログ テンプレート リソース リスト コントロールを追加します。 そのコントロールの ID を指定します

1. 使用して、[メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)型のメンバー変数を追加する`CListCtrl`コントロール プロパティにします。 このメンバーを使用するには、呼び出しと`CListCtrl`メンバー関数。

1. 使用ダイアログ クラスのハンドラー関数をマップするリスト コントロールの通知メッセージの [プロパティ] ウィンドウを処理する必要があります (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)のスタイルを設定、`CListCtrl`します。 参照してください[リスト コントロール スタイルの変更](../mfc/changing-list-control-styles.md)します。 これにより、ビューを後で変更できますが、コントロールでは、取得した"view"の種類を決定します。

### <a name="to-use-clistctrl-in-a-nondialog-window"></a>以外のウィンドウで CListCtrl を使用するには

1. ビューまたはウィンドウのクラスでは、コントロールを定義します。

1. コントロールの呼び出し[作成](../mfc/reference/clistctrl-class.md#create)メンバー関数は、おそらくで[OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)、親ウィンドウの可能性がありますの早期[OnCreate](../mfc/reference/cwnd-class.md#oncreate)いる場合、ハンドラー関数コントロールをサブクラス)。 コントロールのスタイルを設定します。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
