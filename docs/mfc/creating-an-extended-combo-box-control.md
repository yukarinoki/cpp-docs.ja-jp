---
title: 拡張コンボ ボックス コントロールの作成
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
ms.openlocfilehash: d1e81664403f45a0a35cd24ceea16e1425b03403
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668768"
---
# <a name="creating-an-extended-combo-box-control"></a>拡張コンボ ボックス コントロールの作成

拡張コンボ ボックス コントロールを作成する方法は、ダイアログ ボックスで、コントロールの使用または以外のウィンドウで作成するかどうかによって異なります。

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>CComboBoxEx をダイアログ ボックスで直接使用するには

1. ダイアログ エディターでダイアログ テンプレート リソースを拡張コンボ ボックス コントロールを追加します。 そのコントロールの ID を指定します

1. 拡張コンボ ボックス コントロールのプロパティ ダイアログ ボックスを使用して、必要に応じてスタイルを指定します。

1. 使用して、[メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)型のメンバー変数を追加する[CComboBoxEx](../mfc/reference/ccomboboxex-class.md)コントロール プロパティにします。 このメンバーを使用するには、呼び出しと`CComboBoxEx`メンバー関数。

1. [プロパティ] ウィンドウを使用して、任意拡張コンボ ボックス コントロールの通知メッセージを処理する必要があるため、ダイアログ クラスのハンドラー関数にマップする (を参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md))。

1. [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)、追加のスタイルを設定、`CComboBoxEx`オブジェクト。

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>CComboBoxEx を以外のウィンドウで使用するには

1. ビューまたはウィンドウのクラスでは、コントロールを定義します。

1. コントロールの呼び出し[作成](../mfc/reference/ctabctrl-class.md#create)メンバー関数は、おそらくで[OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate)、親ウィンドウの可能性がありますの早期[OnCreate](../mfc/reference/cwnd-class.md#oncreate)ハンドラー関数。 コントロールのスタイルを設定します。

## <a name="see-also"></a>関連項目

[CComboBoxEx の使い方](../mfc/using-ccomboboxex.md)<br/>
[コントロール](../mfc/controls-mfc.md)

