---
title: 'チュートリアル: ツール バーへのコントロールの追加'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: 2a801e61c49301d9b8780bbf7eb77025990337ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360271"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>チュートリアル: ツール バーへのコントロールの追加

この資料では、Windows コントロールを含むツール バー ボタンをツール バーに追加する方法について説明します。 MFC では、ツール[CMFCDropDownToolbarButton Class](../mfc/reference/cmfcdropdowntoolbarbutton-class.md)バー ボタンは[、派生クラス](../mfc/reference/cmfctoolbarbutton-class.md)である必要[があります。](../mfc/reference/cmfctoolbarmenubutton-class.md) [CMFCToolBarComboBoxButton Class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md) [CMFCToolBarEditBoxButton Class](../mfc/reference/cmfctoolbareditboxbutton-class.md)

## <a name="adding-controls-to-toolbars"></a>ツール バーへのコントロールの追加

ツール バーにコントロールを追加するには、次の手順を実行します。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。 Visual Studio の**ツール バー エディター**を使用してボタンを作成する方法の詳細については、「ツール[バー エディター](../windows/toolbar-editor.md) 」を参照してください。

1. 親ツール バーのすべてのビットマップでボタンのツール バー イメージ (ボタン アイコン) を予約します。

1. メッセージを処理するメッセージ ハンドラーで`AFX_WM_RESETTOOLBAR`、次の手順を実行します。

   1. `CMFCToolbarButton` 派生クラスを使用して、ボタン コントロールを作成します。

   1. ダミー ボタンを新しいコントロールに置き換えるには[、CMFC ツール バー::置換ボタン](../mfc/reference/cmfctoolbar-class.md#replacebutton)を使用します。 `ReplaceButton` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックでボタン オブジェクトを作成できます。

> [!NOTE]
> アプリケーションでカスタマイズを有効にした場合は、[**カスタマイズ**] ダイアログ ボックスの [ツール バー] タブにある [**リセット**] ボタンを使用して、再コンパイル後にアプリケーションで更新されたコントロールを表示して **、ツール バー**をリセットする必要があります。 ツール バーの状態は Windows レジストリに保存され、アプリケーションの起動中に `ReplaceButton` メソッドが実行された後、レジストリ情報が読み込まれ適用されます。

## <a name="toolbar-controls-and-customization"></a>ツール バー コントロールとカスタマイズ

[**カスタマイズ**] ダイアログ ボックスの [**コマンド**] タブには、アプリケーションで使用できるコマンドの一覧が表示されます。 既定では、[**カスタマイズ**] ダイアログ ボックスはアプリケーション メニューを処理し、各メニュー カテゴリの標準ツール バー ボタンの一覧を作成します。 ツール バー コントロールの拡張機能を維持するには、[**ユーザー設定**] ダイアログ ボックスの標準ツール バー ボタンをカスタム コントロールに置き換える必要があります。

カスタマイズを有効にすると、カスタマイズ ハンドラー`OnViewCustomize`で[CMFCToolBarsCustomizeDialog クラス クラス](../mfc/reference/cmfctoolbarscustomizedialog-class.md)を使用してカスタマイズ のダイアログ ボックスを作成します。 **Customize** 呼び出すことによって、[**カスタマイズ**] ダイアログ ボックスを表示する前に[、CMFCToolBarsCustomizeDialog::作成を呼び出して、CMFCToolBarsCustomizeDialog::置換ボタン](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)を呼び出して、標準のボタンを新しいコントロールに置き換えます。 [CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create)

## <a name="example-creating-a-find-combo-box"></a>例 : [Find] コンボ ボックスの作成

ここでは、ツールバーに表示され、最近使用した検索文字列を含む**Find**コンボ ボックス コントロールを作成する方法について説明します。 ユーザーはコントロールに文字列を入力した後、Enter キーを押してドキュメントを検索するか、Esc キーを押してフォーカスをメイン フレームに戻します。 この例では、ドキュメントが[CEditView クラス](../mfc/reference/ceditview-class.md)派生ビューで表示されることを前提としています。

### <a name="creating-the-find-control"></a>Find コントロールの作成

まず、**検索**コンボ ボックス コントロールを作成します。

1. アプリケーション リソースにボタンとコマンドを追加します。

   1. アプリケーション リソースで、`ID_EDIT_FIND` コマンド ID を持つ新しいボタンをアプリケーションのツール バー、およびツール バーに関連付けられたビットマップに追加します。

   1. コマンド ID を使用して`ID_EDIT_FIND`新しいメニュー項目を作成します。

   1. 新しい文字列 "Find the text\nFind" を文字列テーブルに追加し、`ID_EDIT_FIND_COMBO` コマンド ID を割り当てます。 この ID は、[**検索**] コンボ ボックス ボタンのコマンド ID として使用されます。

        > [!NOTE]
        > `ID_EDIT_FIND` は `CEditView` によって処理される標準のコマンドであるため、このコマンド用の特別なハンドラーを実装する必要はありません。  ただし、新しいコマンド `ID_EDIT_FIND_COMBO` のハンドラーを実装する必要があります。

1. [CComboBox](../mfc/reference/ccombobox-class.md)クラス`CFindComboBox`から派生した新しいクラスを作成します。

1. `CFindComboBox` クラスで、`PreTranslateMessage` 仮想メソッドをオーバーライドします。 このメソッドを使用すると、コンボ ボックスが[WM_KEYDOWN](/windows/win32/inputdev/wm-keydown)メッセージを処理できるようになります。 ユーザーが Esc キーを押す (`VK_ESCAPE`) と、フォーカスがメイン フレーム ウィンドウに戻ります。 ユーザーが Enter キーを押す (`VK_ENTER`) と、`WM_COMMAND` コマンド ID を含む `ID_EDIT_FIND_COMBO` メッセージがメイン フレーム ウィンドウにポストされます。

1. から派生したコンボ ボックスの**検索**コンボ ボックス[ボタンのクラスを作成します](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)。 この例では、それには `CFindComboButton` という名前が付いています。

1. `CMFCToolbarComboBoxButton` のコンストラクターは、3 つのパラメーター (ボタンのコマンド ID、ボタン イメージのインデックス、およびコンボ ボックスのスタイル) を受け取ります。 これらのパラメーターを次のように設定します。

   1. `ID_EDIT_FIND_COMBO` をコマンド ID として渡します。

   1. イメージ インデックスを取得するには[、CCommandManager::GetCmdImage](reference/internal-classes.md)を使用`ID_EDIT_FIND`します。

   1. 使用可能なコンボ ボックス スタイルの一覧については、「[コンボ ボックススタイル](../mfc/reference/styles-used-by-mfc.md#combo-box-styles)」を参照してください。

1. `CFindComboButton` クラスで、`CMFCToolbarComboBoxButton::CreateCombo` メソッドをオーバーライドします。 ここで、`CFindComboButton` オブジェクトを作成し、オブジェクトへのポインターを返す必要があります。

1. [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial)マクロを使用して、コンボボタンを永続的にします。 ワークスペース マネージャーは、ボタンの状態を自動的に読み込み、Windows レジストリに保存します。

1. ドキュメント ビューで `ID_EDIT_FIND_COMBO` ハンドラーを実装します。 すべての**検索**コンボ ボックス ボタンを取得するには[、CMFC ツール バー::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons)を使用`ID_EDIT_FIND_COMBO`します。 カスタマイズにより、同じコマンド ID を持つ複数のボタンが存在する可能性があります。

1. メッセージ ハンドラー`OnFind`で、検索コマンドが [**検索**] コンボ ボックス ボタンから送信されたかどうかを判断するのに[は CMFC ツール バー::IsLastCommandFrom ボタン](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton)を使用します。 `ID_EDIT_FIND` 該当する場合は、テキストを検索し、検索文字列をコンボ ボックスに追加します。

### <a name="adding-the-find-control-to-the-main-toolbar"></a>メイン ツール バーへの Find コントロールの追加

ツール バーにコンボ ボックス ボタンを追加するには、次の手順を実行します。

1. メイン フレーム ウィンドウに `AFX_WM_RESETTOOLBAR` メッセージ ハンドラー `OnToolbarReset` を実装します。

    > [!NOTE]
    > アプリケーションの起動中にツール バーが初期化されたとき、またはカスタマイズ中にツール バーがリセットされたときに、フレームワークはこのメッセージをメイン フレーム ウィンドウに送信します。 いずれの場合も、標準のツール バー ボタンをカスタム**の [検索**] コンボ ボックス ボタンに置き換える必要があります。

1. ハンドラーで`AFX_WM_RESETTOOLBAR`、ツールバー ID、つまりAFX_WM_RESETTOOLBARメッセージの*WPARAM*を調べます。 ツール バー ID が **[検索**] コンボ ボックス ボタンを含むツール バーの ID と同じ場合は[、CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton)を`ID_EDIT_FIND)`呼び`CFindComboButton`出して **[検索**] ボタン (つまり、ボタンをコマンド ID をオブジェクトに置き換えます)。

    > [!NOTE]
    > `CFindComboBox` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックで `ReplaceButton` オブジェクトを作成できます。

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>[カスタマイズ] ダイアログ ボックスへの Find コントロールの追加

カスタマイズ`OnViewCustomize`ハンドラーで呼び出す[CMFCToolBarsCustomizeDialog::置換ボタン](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)を呼び出して **、[検索**] ボタン (`ID_EDIT_FIND`つまり、ボタン`CFindComboButton`をコマンド ID) に置き換えます。

## <a name="see-also"></a>関連項目

[階層グラフ](../mfc/hierarchy-chart.md)<br/>
[クラス](../mfc/reference/mfc-classes.md)<br/>
[クラス](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton クラス](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton クラス](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[クラスをカスタマイズします。](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
