---
title: 拡張コンボ ボックス コントロールの作成
ms.date: 11/04/2016
helpviewer_keywords:
- extended combo boxes
- CComboBoxEx class [MFC], creating extended combo box controls
- extended combo boxes [MFC], creating
ms.assetid: a964267e-97b6-4e77-9f89-55bb5c68913f
ms.openlocfilehash: 554085304f5330ac9cd99a5b814af26ce3a9c7e6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616283"
---
# <a name="creating-an-extended-combo-box-control"></a>拡張コンボ ボックス コントロールの作成

拡張コンボボックスコントロールの作成方法は、ダイアログボックスでコントロールを使用しているか、nondialog ウィンドウで作成したかによって異なります。

### <a name="to-use-ccomboboxex-directly-in-a-dialog-box"></a>ダイアログボックスで CComboBoxEx を直接使用するには

1. ダイアログエディターで、ダイアログテンプレートリソースに拡張コンボボックスコントロールを追加します。 コントロール ID を指定します。

1. 拡張コンボボックスコントロールの [プロパティ] ダイアログボックスを使用して、必要なスタイルを指定します。

1. [メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)を使用して、 [CComboBoxEx](reference/ccomboboxex-class.md)型のメンバー変数をコントロールプロパティに追加します。 このメンバーを使用して、メンバー関数を呼び出すことができ `CComboBoxEx` ます。

1. [クラスウィザード](reference/mfc-class-wizard.md)を使用して、処理する必要がある拡張コンボボックスコントロールの通知メッセージのダイアログクラスのハンドラー関数をマップします (「[関数へのメッセージのマッピング](reference/mapping-messages-to-functions.md)」を参照してください)。

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)で、オブジェクトの追加のスタイルを設定し `CComboBoxEx` ます。

### <a name="to-use-ccomboboxex-in-a-nondialog-window"></a>Nondialog ウィンドウで CComboBoxEx を使用するには

1. ビューまたはウィンドウクラスでコントロールを定義します。

1. [OnInitialUpdate](reference/cview-class.md#oninitialupdate)のように、コントロールの[Create](reference/ctabctrl-class.md#create) member 関数を呼び出します (おそらく、親ウィンドウの[OnCreate](reference/cwnd-class.md#oncreate) handler 関数と同じようにします)。 コントロールのスタイルを設定します。

## <a name="see-also"></a>関連項目

[CComboBoxEx の使い方](using-ccomboboxex.md)<br/>
[制限](controls-mfc.md)
