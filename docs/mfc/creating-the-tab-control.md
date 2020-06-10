---
title: タブ コントロールの作成
ms.date: 11/04/2016
f1_keywords:
- TCS_EX_REGISTERDROP
- TCS_EX_FLATSEPARATORS
helpviewer_keywords:
- TCS_EX_REGISTERDROP extended style [MFC]
- tab controls [MFC], creating
- CTabCtrl class [MFC], creating
- TCS_EX_FLATSEPARATORS extended style
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
ms.openlocfilehash: 6d5aa6873966ecb4c845f1c503b24c07b6c0c7a3
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619605"
---
# <a name="creating-the-tab-control"></a>タブ コントロールの作成

タブコントロールの作成方法は、ダイアログボックスでコントロールを使用しているか、nondialog ウィンドウで作成したかによって異なります。

### <a name="to-use-ctabctrl-directly-in-a-dialog-box"></a>ダイアログボックスで CTabCtrl を直接使用するには

1. ダイアログエディターで、ダイアログテンプレートリソースにタブコントロールを追加します。 コントロール ID を指定します。

1. [メンバー変数の追加ウィザード](../ide/adding-a-member-variable-visual-cpp.md)を使用して、コントロールプロパティを持つ[CTabCtrl](reference/ctabctrl-class.md)型のメンバー変数を追加します。 このメンバーを使用して、メンバー関数を呼び出すことができ `CTabCtrl` ます。

1. 処理する必要があるすべてのタブコントロール通知メッセージのダイアログクラスのマップハンドラー関数。 詳細については、「[関数へのメッセージのマッピング](reference/mapping-messages-to-functions.md)」を参照してください。

1. [OnInitDialog](reference/cdialog-class.md#oninitdialog)で、のスタイルを設定し `CTabCtrl` ます。

### <a name="to-use-ctabctrl-in-a-nondialog-window"></a>Nondialog ウィンドウで CTabCtrl を使用するには

1. ビューまたはウィンドウクラスでコントロールを定義します。

1. コントロールの Create member 関数を呼び出します。これは、おそらく親ウィンドウの[OnCreate](reference/cwnd-class.md#oncreate) handler 関数 (コントロールをサブクラス化している場合) のように、 [OnInitialUpdate](reference/cview-class.md#oninitialupdate)で[作成](reference/ctabctrl-class.md#create)します。 コントロールのスタイルを設定します。

`CTabCtrl`オブジェクトが作成された後、次の拡張スタイルを設定またはクリアできます。

- **TCS_EX_FLATSEPARATORS**タブコントロールは、タブ項目間の区切り記号を描画します。 この拡張スタイルは、 **TCS_BUTTONS**と**TCS_FLATBUTTONS**スタイルを持つタブコントロールにのみ影響します。 既定では、 **TCS_FLATBUTTONS**スタイルを使用してタブコントロールを作成すると、この拡張スタイルが設定されます。

- **TCS_EX_REGISTERDROP**Tab コントロールは**TCN_GETOBJECT**通知メッセージを生成して、コントロールのタブ項目の上にオブジェクトをドラッグしたときにドロップ先オブジェクトを要求します。

    > [!NOTE]
    >  **TCN_GETOBJECT**通知を受信するには、 [AfxOleInit](reference/ole-initialization.md#afxoleinit)を呼び出すことによって、OLE ライブラリを初期化する必要があります。

これらのスタイルは、コントロールが作成された後、 [Getextendedstyle](reference/ctabctrl-class.md#getextendedstyle)および[SetExtendedStyle](reference/ctabctrl-class.md#setextendedstyle)メンバー関数を呼び出すことによって取得および設定できます。

たとえば、次のコード行を使用して**TCS_EX_FLATSEPARATORS**スタイルを設定します。

[!code-cpp[NVC_MFCControlLadenDialog#33](codesnippet/cpp/creating-the-tab-control_1.cpp)]

**TCS_EX_FLATSEPARATORS** `CTabCtrl` 次のコード行を使用して、オブジェクトから TCS_EX_FLATSEPARATORS スタイルをクリアします。

[!code-cpp[NVC_MFCControlLadenDialog#34](codesnippet/cpp/creating-the-tab-control_2.cpp)]

これにより、オブジェクトのボタン間に表示される区切り記号が削除され `CTabCtrl` ます。

## <a name="see-also"></a>関連項目

[CTabCtrl の使い方](using-ctabctrl.md)<br/>
[制限](controls-mfc.md)
