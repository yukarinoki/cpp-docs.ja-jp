---
title: 'チュートリアル: ツールバーのコントロールの追加'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: 0b5b8685b3062bf63187a765b7e90e26f8c65681
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62392454"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>チュートリアル: ツールバーのコントロールの追加

この記事では、ツールバーに、Windows コントロールを含むツール バー ボタンを追加する方法について説明します。 Mfc では、ツール バー ボタンがある必要があります、 [CMFCToolBarButton クラス](../mfc/reference/cmfctoolbarbutton-class.md)-たとえば、クラスを派生[CMFCToolBarComboBoxButton クラス](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)、 [CMFCToolBarEditBoxButton クラス](../mfc/reference/cmfctoolbareditboxbutton-class.md)、[CMFCDropDownToolbarButton クラス](../mfc/reference/cmfcdropdowntoolbarbutton-class.md)、または[CMFCToolBarMenuButton クラス](../mfc/reference/cmfctoolbarmenubutton-class.md)します。

## <a name="adding-controls-to-toolbars"></a>ツール バーへのコントロールの追加

ツール バーにコントロールを追加するには、次の手順を実行します。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。 使用してボタンを作成する方法について、**ツール バー エディター** Visual Studio で、次を参照してください。、[ツール バー エディター](../windows/toolbar-editor.md)記事。

1. 親ツール バーのすべてのビットマップでボタンのツール バー イメージ (ボタン アイコン) を予約します。

1. 処理するメッセージ ハンドラーで、`AFX_WM_RESETTOOLBAR`メッセージで、次の手順を実行します。

   1. `CMFCToolbarButton` 派生クラスを使用して、ボタン コントロールを作成します。

   1. 使用して、ダミー ボタンを新しいコントロールに置き換える[CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton)します。 `ReplaceButton` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックでボタン オブジェクトを作成できます。

> [!NOTE]
>  使用して、ツールバーのリセットを必要に応じて、アプリケーションのカスタマイズを有効にした場合、**リセット**ボタンを**ツールバー**のタブ、**カスタマイズ**ダイアログ ボックスを参照してください、再コンパイルした後、アプリケーションでコントロールを更新します。 ツール バーの状態は Windows レジストリに保存され、アプリケーションの起動中に `ReplaceButton` メソッドが実行された後、レジストリ情報が読み込まれ適用されます。

## <a name="toolbar-controls-and-customization"></a>ツール バー コントロールとカスタマイズ

**コマンド**のタブ、**カスタマイズ** ダイアログ ボックスに、アプリケーションで使用できるコマンドの一覧が含まれています。 既定で、**カスタマイズ** ダイアログ ボックスは、アプリケーション メニューを処理し、各メニュー カテゴリで標準ツール バー ボタンのリストを構築します。 ツール バー コントロールを提供する拡張機能を保持するでカスタム コントロールの標準ツール バー ボタンを置き換える必要があります、**カスタマイズ** ダイアログ ボックス。

作成したカスタマイズを有効にすると、**カスタマイズ** ダイアログ ボックスで、カスタマイズ ハンドラー`OnViewCustomize`を使用して、 [CMFCToolBarsCustomizeDialog クラス](../mfc/reference/cmfctoolbarscustomizedialog-class.md)クラス。 表示する前に、**カスタマイズ** ダイアログ ボックスを呼び出して[CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create)、呼び出す[CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)を置き換える新しいコントロールに標準のボタン。

## <a name="example-creating-a-find-combo-box"></a>例:検索コンボ ボックスの作成

このセクションを作成する方法を説明します、**検索**コンボ ボックス コントロールをツールバーに表示され、最近使用した検索文字列が含まれています。 ユーザーはコントロールに文字列を入力した後、Enter キーを押してドキュメントを検索するか、Esc キーを押してフォーカスをメイン フレームに戻します。 この例では、ドキュメントに表示されることを[CEditView クラス](../mfc/reference/ceditview-class.md)-派生ビュー。

### <a name="creating-the-find-control"></a>Find コントロールの作成

最初に、作成、**検索**コンボ ボックス コントロール。

1. アプリケーション リソースにボタンとコマンドを追加します。

   1. アプリケーション リソースで、`ID_EDIT_FIND` コマンド ID を持つ新しいボタンをアプリケーションのツール バー、およびツール バーに関連付けられたビットマップに追加します。

   1. 新しいメニュー項目を作成、`ID_EDIT_FIND`コマンド ID

   1. 新しい文字列 "Find the text\nFind" を文字列テーブルに追加し、`ID_EDIT_FIND_COMBO` コマンド ID を割り当てます。 この ID がのコマンド ID として使用される、**検索**コンボ ボックス ボタンをクリックします。

        > [!NOTE]
        > `ID_EDIT_FIND` は `CEditView` によって処理される標準のコマンドであるため、このコマンド用の特別なハンドラーを実装する必要はありません。  ただし、新しいコマンド `ID_EDIT_FIND_COMBO` のハンドラーを実装する必要があります。

1. 新しいクラスを作成`CFindComboBox`から派生した[CComboBox クラス](../mfc/reference/ccombobox-class.md)します。

1. `CFindComboBox` クラスで、`PreTranslateMessage` 仮想メソッドをオーバーライドします。 このメソッドは、処理するコンボ ボックスを有効になります、 [WM_KEYDOWN](/windows/desktop/inputdev/wm-keydown)メッセージ。 ユーザーが Esc キーを押す (`VK_ESCAPE`) と、フォーカスがメイン フレーム ウィンドウに戻ります。 ユーザーが Enter キーを押す (`VK_ENTER`) と、`WM_COMMAND` コマンド ID を含む `ID_EDIT_FIND_COMBO` メッセージがメイン フレーム ウィンドウにポストされます。

1. クラスを作成、**検索**から派生した、コンボ ボックス ボタン[CMFCToolBarComboBoxButton クラス](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)します。 この例では、それには `CFindComboButton` という名前が付いています。

1. `CMFCToolbarComboBoxButton` のコンストラクターは、3 つのパラメーター (ボタンのコマンド ID、ボタン イメージのインデックス、およびコンボ ボックスのスタイル) を受け取ります。 これらのパラメーターを次のように設定します。

   1. `ID_EDIT_FIND_COMBO` をコマンド ID として渡します。

   1. 使用[CCommandManager::GetCmdImage](reference/internal-classes.md)で`ID_EDIT_FIND`イメージ インデックスを取得します。

   1. 使用可能なコンボ ボックス スタイルの一覧は、次を参照してください。[コンボ ボックス スタイル](../mfc/reference/styles-used-by-mfc.md#combo-box-styles)します。

1. `CFindComboButton` クラスで、`CMFCToolbarComboBoxButton::CreateCombo` メソッドをオーバーライドします。 ここで、`CFindComboButton` オブジェクトを作成し、オブジェクトへのポインターを返す必要があります。

1. 使用して、 [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial)コンボ ボタンで持続されるようにするマクロ。 ワークスペース マネージャーは、ボタンの状態を自動的に読み込み、Windows レジストリに保存します。

1. ドキュメント ビューで `ID_EDIT_FIND_COMBO` ハンドラーを実装します。 使用[CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons)で`ID_EDIT_FIND_COMBO`をすべて取得する**検索**コンボ ボックス ボタン。 カスタマイズにより、同じコマンド ID を持つ複数のボタンが存在する可能性があります。

1. `ID_EDIT_FIND`メッセージ ハンドラー`OnFind`を使用して、 [CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton)から検索 コマンドが送信されたかどうかを判断する、**検索**コンボ ボックス ボタンをクリックします。 該当する場合は、テキストを検索し、検索文字列をコンボ ボックスに追加します。

### <a name="adding-the-find-control-to-the-main-toolbar"></a>メイン ツール バーへの Find コントロールの追加

ツール バーにコンボ ボックス ボタンを追加するには、次の手順を実行します。

1. メイン フレーム ウィンドウに `AFX_WM_RESETTOOLBAR` メッセージ ハンドラー `OnToolbarReset` を実装します。

    > [!NOTE]
    > アプリケーションの起動中にツール バーが初期化されたとき、またはカスタマイズ中にツール バーがリセットされたときに、フレームワークはこのメッセージをメイン フレーム ウィンドウに送信します。 いずれの場合も、カスタムの標準ツール バー ボタンを置き換える必要があります**検索**コンボ ボックス ボタンをクリックします。

1. `AFX_WM_RESETTOOLBAR`ハンドラー、つまり、ツールバー ID を調べて、 *WPARAM* AFX_WM_RESETTOOLBAR メッセージの。 ツールバー ID が入っているツールバーの場合、**検索**コンボ ボックス ボタン、呼び出し[CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton)を置き換える、**検索**ボタン (これは、コマンド ID を持つボタン`ID_EDIT_FIND)`で、`CFindComboButton`オブジェクト。

    > [!NOTE]
    > `CFindComboBox` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックで `ReplaceButton` オブジェクトを作成できます。

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>[カスタマイズ] ダイアログ ボックスへの Find コントロールの追加

カスタマイズ ハンドラーで`OnViewCustomize`、呼び出す[CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)を置き換える、**検索**ボタン (コマンド ID を持つボタン`ID_EDIT_FIND`)、で`CFindComboButton`オブジェクト。

## <a name="see-also"></a>関連項目

[階層図](../mfc/hierarchy-chart.md)<br/>
[クラス](../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar クラス](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton クラス](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton クラス](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBarsCustomizeDialog クラス](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
