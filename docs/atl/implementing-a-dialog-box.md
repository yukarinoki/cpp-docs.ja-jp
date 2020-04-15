---
title: ダイアログ ボックスの実装
ms.date: 11/04/2016
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
ms.openlocfilehash: 435926b0a0affde03580ceb2b479cb08a17d0454
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319473"
---
# <a name="implementing-a-dialog-box"></a>ダイアログ ボックスの実装

ATL プロジェクトにダイアログ ボックスを追加するには、ATL ダイアログ ウィザードを使用する方法と手動で追加する方法の 2 つがあります。

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>ATL ダイアログ ウィザードを使用したダイアログ ボックスの追加

[[クラスの追加] ダイアログ ボックス](../ide/add-class-dialog-box.md)で、ATL ダイアログ オブジェクトを選択して、ATL プロジェクトにダイアログ ボックスを追加します。 必要に応じて ATL ダイアログ ウィザードに入力し、[**完了**] をクリックします。 ウィザードは、プロジェクトに[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)から派生したクラスを追加します。 [**表示**] メニューから **[リソース ビュー** ] を開き、ダイアログをダブルクリックしてリソース エディタで開きます。

> [!NOTE]
> からダイアログ ボックスが派生する`CAxDialogImpl`場合は、ActiveX コントロールと Windows コントロールの両方をホストできます。 ダイアログ ボックス クラスで ActiveX コントロールのサポートのオーバーヘッドが必要ない場合は、代わりに[CSimpleDialog](../atl/reference/csimpledialog-class.md)または[CDialogImpl を](../atl/reference/cdialogimpl-class.md)使用します。

メッセージ ハンドラーとイベント ハンドラーは、クラス ビューからダイアログ クラスに追加できます。 詳細については、「 [ATL メッセージ ハンドラの追加](../atl/adding-an-atl-message-handler.md)」を参照してください。

## <a name="adding-a-dialog-box-manually"></a>ダイアログ ボックスを手動で追加する

ダイアログ ボックスの実装は、ウィンドウの実装と似ています。 クラスを派生させる[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) [、CDialogImpl、](../atl/reference/cdialogimpl-class.md)または[CSimpleDialog のいずれかを](../atl/reference/csimpledialog-class.md)使用して、メッセージを処理する[メッセージ マップ](../atl/message-maps-atl.md)を宣言します。 ただし、派生クラスでダイアログ テンプレート リソース ID も指定する必要があります。 この値を保持するには、クラスに`IDD`データ メンバーが呼び出されている必要があります。

> [!NOTE]
> ATL ダイアログ ウィザードを使用してダイアログ ボックスを作成すると、ウィザードによって`IDD`メンバが**列挙**型として自動的に追加されます。

`CDialogImpl`Windows コントロールをホストするモーダル またはモードレス ダイアログ ボックスを実装できます。 `CAxDialogImpl`では、ActiveX コントロールと Windows コントロールの両方をホストするモーダル ダイアログ ボックスまたはモードレス ダイアログ ボックスを実装できます。

モーダル ダイアログ ボックスを作成するには、派生`CDialogImpl`(または`CAxDialogImpl`-derived) クラスのインスタンスを作成し[、DoModal](../atl/reference/cdialogimpl-class.md#domodal)メソッドを呼び出します。 モーダル ダイアログ ボックスを閉じるには、メッセージ ハンドラーから[EndDialog](../atl/reference/cdialogimpl-class.md#enddialog)メソッドを呼び出します。 モードレス ダイアログ ボックスを作成するには、[Create](../atl/reference/cdialogimpl-class.md#create)の代わりに`DoModal`Create メソッドを呼び出します。 モードレス ダイアログ ボックスを破棄するには[、DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow)を呼び出します。

シンク イベントは[、CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)で自動的に行われます。 派生クラスのハンドラーと同じ方法で、ダイアログ ボックスのメッセージ`CWindowImpl`ハンドラーを実装します。 メッセージ固有の戻り値がある場合は、 として返します`LRESULT`。 返される`LRESULT`値は、Windows ダイアログ マネージャーによって適切に処理するために ATL によってマップされます。 詳細については、atlwin.h の[CDialogImplBaseT::DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc)のソース コードを参照してください。

## <a name="example"></a>例

次のクラスは、ダイアログ ボックスを実装します。

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>関連項目

[ウィンドウクラス](../atl/atl-window-classes.md)
