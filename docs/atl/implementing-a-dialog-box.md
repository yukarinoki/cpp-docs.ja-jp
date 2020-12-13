---
description: 詳細については、「ダイアログボックスの実装」を参照してください。
title: ダイアログボックスの実装
ms.date: 11/04/2016
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
ms.openlocfilehash: 736619b39d06cffc28bc9723c94d0c5367dd51d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152911"
---
# <a name="implementing-a-dialog-box"></a>ダイアログボックスの実装

ATL プロジェクトにダイアログボックスを追加するには、ATL ダイアログウィザードを使用する方法と、手動で追加する方法の2つの方法があります。

## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>ATL ダイアログウィザードを使用したダイアログボックスの追加

[ [クラスの追加] ダイアログボックス](../ide/adding-a-class-visual-cpp.md#add-class-dialog-box)で、atl プロジェクトにダイアログボックスを追加する atl ダイアログオブジェクトを選択します。 必要に応じて ATL ダイアログウィザードに入力し、[ **完了**] をクリックします。 ウィザードによって、 [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) から派生したクラスがプロジェクトに追加されます。 [**表示**] メニューから **リソースビュー** を開き、ダイアログを見つけてダブルクリックし、リソースエディターで開きます。

> [!NOTE]
> ダイアログボックスがから派生している場合は `CAxDialogImpl` 、ActiveX と Windows の両方のコントロールをホストできます。 ダイアログボックスクラスで ActiveX コントロールのサポートのオーバーヘッドを避けたい場合は、代わりに [CSimpleDialog](../atl/reference/csimpledialog-class.md) または [CDialogImpl](../atl/reference/cdialogimpl-class.md) を使用してください。

メッセージおよびイベントハンドラーは、クラスビューからダイアログクラスに追加できます。 詳細については、「 [ATL メッセージハンドラーの追加](../atl/adding-an-atl-message-handler.md)」を参照してください。

## <a name="adding-a-dialog-box-manually"></a>手動によるダイアログボックスの追加

ダイアログボックスの実装は、ウィンドウの実装に似ています。 [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)、 [CDialogImpl](../atl/reference/cdialogimpl-class.md)、または[CSimpleDialog](../atl/reference/csimpledialog-class.md)のいずれかからクラスを派生させ、メッセージを処理する[メッセージマップ](../atl/message-maps-atl.md)を宣言します。 ただし、派生クラスでダイアログテンプレートリソース ID も指定する必要があります。 クラスには、 `IDD` この値を保持するためにというデータメンバーが必要です。

> [!NOTE]
> ATL ダイアログウィザードを使用してダイアログボックスを作成すると、ウィザードによっ `IDD` てメンバーが型として自動的に追加され **`enum`** ます。

`CDialogImpl` Windows コントロールをホストするモーダルまたはモードレスのダイアログボックスを実装できます。 `CAxDialogImpl` ActiveX と Windows の両方のコントロールをホストするモーダルまたはモードレスのダイアログボックスを実装できます。

モーダルダイアログボックスを作成するに `CDialogImpl` は、派生クラスまたは派生クラスのインスタンスを作成 `CAxDialogImpl` してから、 [DoModal](../atl/reference/cdialogimpl-class.md#domodal) メソッドを呼び出します。 モーダルダイアログボックスを閉じるには、メッセージハンドラーから [EndDialog](../atl/reference/cdialogimpl-class.md#enddialog) メソッドを呼び出します。 モードレスダイアログボックスを作成するには、の代わりに [create](../atl/reference/cdialogimpl-class.md#create) メソッドを呼び出し `DoModal` ます。 モードレスダイアログボックスを破棄するには、 [DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow)を呼び出します。

シンクイベントは、 [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)で自動的に実行されます。 派生クラスのハンドラーと同じように、ダイアログボックスのメッセージハンドラーを実装し `CWindowImpl` ます。 メッセージ固有の戻り値がある場合は、として返し `LRESULT` ます。 返された `LRESULT` 値は、Windows ダイアログマネージャーによる適切な処理のために ATL によってマップされます。 詳細については、「 [CDialogImplBaseT::D ialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) 」のソースコードを参照してください。

## <a name="example"></a>例

次のクラスは、ダイアログボックスを実装します。

[!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]

## <a name="see-also"></a>関連項目

[ウィンドウクラス](../atl/atl-window-classes.md)
