---
description: '詳細については、「チュートリアル: ツールバーにコントロールを配置する」を参照してください。'
title: 'チュートリアル: ツール バーへのコントロールの追加'
ms.date: 04/25/2019
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
ms.openlocfilehash: eafb1afa2ffffeaaabfc6b463e2951d8d532db58
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143053"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>チュートリアル: ツール バーへのコントロールの追加

この記事では、Windows コントロールを含むツールバーボタンをツールバーに追加する方法について説明します。 MFC では、ツールバーボタンは、 [CMFCToolBarComboBoxButton class](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)、 [CMFCToolBarEditBoxButton Class](../mfc/reference/cmfctoolbareditboxbutton-class.md)、 [CMFCDropDownToolbarButton Class](../mfc/reference/cmfcdropdowntoolbarbutton-class.md)、 [Cmfctoolbarmenubutton クラス](../mfc/reference/cmfctoolbarmenubutton-class.md)など、 [CMFCToolBarButton クラス](../mfc/reference/cmfctoolbarbutton-class.md)の派生クラスである必要があります。

## <a name="adding-controls-to-toolbars"></a>ツール バーへのコントロールの追加

ツール バーにコントロールを追加するには、次の手順を実行します。

1. 親ツール バー リソースでボタンのダミー リソース ID を予約します。 Visual Studio の **ツールバーエディター** を使用してボタンを作成する方法の詳細については、 [ツールバーエディター](../windows/toolbar-editor.md) の記事を参照してください。

1. 親ツール バーのすべてのビットマップでボタンのツール バー イメージ (ボタン アイコン) を予約します。

1. メッセージを処理するメッセージハンドラーで `AFX_WM_RESETTOOLBAR` 、次の手順を実行します。

   1. `CMFCToolbarButton` 派生クラスを使用して、ボタン コントロールを作成します。

   1. [Cmfctoolbar:: ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton)を使用して、ダミーのボタンを新しいコントロールに置き換えます。 `ReplaceButton` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックでボタン オブジェクトを作成できます。

> [!NOTE]
> アプリケーションでカスタマイズを有効にした場合、再コンパイル後にアプリケーションで更新されたコントロールを表示するには、[**カスタマイズ**] ダイアログボックスの [**ツールバー** ] タブにある [**リセット**] ボタンを使用して、ツールバーをリセットする必要がある場合があります。 ツール バーの状態は Windows レジストリに保存され、アプリケーションの起動中に `ReplaceButton` メソッドが実行された後、レジストリ情報が読み込まれ適用されます。

## <a name="toolbar-controls-and-customization"></a>ツール バー コントロールとカスタマイズ

[**カスタマイズ**] ダイアログボックスの [**コマンド**] タブには、アプリケーションで使用できるコマンドの一覧が表示されます。 既定では、[ **ユーザー設定** ] ダイアログボックスはアプリケーションメニューを処理し、各メニューカテゴリの標準ツールバーボタンの一覧を作成します。 ツールバーコントロールによって提供される拡張機能を維持するには、標準ツールバーボタンを [ **カスタマイズ** ] ダイアログボックスのカスタムコントロールに置き換える必要があります。

カスタマイズを有効にする場合は、  `OnViewCustomize` [Cmfctoolbarscustomizedialog クラス](../mfc/reference/cmfctoolbarscustomizedialog-class.md)クラスを使用して、カスタマイズハンドラーで [カスタマイズ] ダイアログボックスを作成します。 [Cmfctoolbarscustomizedialog:: Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create)を呼び出して [**カスタマイズ**] ダイアログボックスを表示する前に、 [Cmfctoolbarscustomizedialog:: replacebutton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)を呼び出して、標準ボタンを新しいコントロールに置き換えます。

## <a name="example-creating-a-find-combo-box"></a>例 : [Find] コンボ ボックスの作成

このセクションでは、ツールバーに表示され、最近使用した検索文字列が含まれている [ **検索** ] コンボボックスコントロールを作成する方法について説明します。 ユーザーはコントロールに文字列を入力した後、Enter キーを押してドキュメントを検索するか、Esc キーを押してフォーカスをメイン フレームに戻します。 この例では、ドキュメントが [CEditView クラス](../mfc/reference/ceditview-class.md)の派生ビューに表示されていることを前提としています。

### <a name="creating-the-find-control"></a>Find コントロールの作成

まず、[ **検索** ] コンボボックスコントロールを作成します。

1. アプリケーション リソースにボタンとコマンドを追加します。

   1. アプリケーション リソースで、`ID_EDIT_FIND` コマンド ID を持つ新しいボタンをアプリケーションのツール バー、およびツール バーに関連付けられたビットマップに追加します。

   1. コマンド ID を使用して、新しいメニュー項目を作成 `ID_EDIT_FIND` します。

   1. 新しい文字列 "Find the text\nFind" を文字列テーブルに追加し、`ID_EDIT_FIND_COMBO` コマンド ID を割り当てます。 この ID は、[ **検索** ] コンボボックスボタンのコマンド id として使用されます。

        > [!NOTE]
        > `ID_EDIT_FIND` は `CEditView` によって処理される標準のコマンドであるため、このコマンド用の特別なハンドラーを実装する必要はありません。  ただし、新しいコマンド `ID_EDIT_FIND_COMBO` のハンドラーを実装する必要があります。

1. `CFindComboBox` [CComboBox クラス](../mfc/reference/ccombobox-class.md)から派生した新しいクラスを作成します。

1. `CFindComboBox` クラスで、`PreTranslateMessage` 仮想メソッドをオーバーライドします。 このメソッドを使用すると、コンボボックスで [WM_KEYDOWN](/windows/win32/inputdev/wm-keydown) メッセージを処理できるようになります。 ユーザーが Esc キーを押す (`VK_ESCAPE`) と、フォーカスがメイン フレーム ウィンドウに戻ります。 ユーザーが Enter キーを押す (`VK_ENTER`) と、`WM_COMMAND` コマンド ID を含む `ID_EDIT_FIND_COMBO` メッセージがメイン フレーム ウィンドウにポストされます。

1. [CMFCToolBarComboBoxButton クラス](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)から派生した [**検索**] コンボボックスボタンのクラスを作成します。 この例では、それには `CFindComboButton` という名前が付いています。

1. `CMFCToolbarComboBoxButton` のコンストラクターは、3 つのパラメーター (ボタンのコマンド ID、ボタン イメージのインデックス、およびコンボ ボックスのスタイル) を受け取ります。 これらのパラメーターを次のように設定します。

   1. `ID_EDIT_FIND_COMBO` をコマンド ID として渡します。

   1. で [Ccommandmanager:: GetCmdImage](reference/internal-classes.md) を使用して `ID_EDIT_FIND` 、イメージのインデックスを取得します。

   1. 使用可能なコンボボックススタイルの一覧については、「 [コンボボックススタイル](../mfc/reference/styles-used-by-mfc.md#combo-box-styles)」を参照してください。

1. `CFindComboButton` クラスで、`CMFCToolbarComboBoxButton::CreateCombo` メソッドをオーバーライドします。 ここで、`CFindComboButton` オブジェクトを作成し、オブジェクトへのポインターを返す必要があります。

1. [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial)マクロを使用して、コンボボタンを持続させることができます。 ワークスペース マネージャーは、ボタンの状態を自動的に読み込み、Windows レジストリに保存します。

1. ドキュメント ビューで `ID_EDIT_FIND_COMBO` ハンドラーを実装します。 すべて [](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons)の `ID_EDIT_FIND_COMBO` **検索** コンボボックスボタンを取得するには、cmfctoolbar:: GetCommandButtons with を使用します。 カスタマイズにより、同じコマンド ID を持つ複数のボタンが存在する可能性があります。

1. `ID_EDIT_FIND`メッセージハンドラーで、 `OnFind` [Cmfctoolbar:: IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton)を使用して、検索コマンドが [**検索**] コンボボックスから送信されたかどうかを確認します。 該当する場合は、テキストを検索し、検索文字列をコンボ ボックスに追加します。

### <a name="adding-the-find-control-to-the-main-toolbar"></a>メイン ツール バーへの Find コントロールの追加

ツール バーにコンボ ボックス ボタンを追加するには、次の手順を実行します。

1. メイン フレーム ウィンドウに `AFX_WM_RESETTOOLBAR` メッセージ ハンドラー `OnToolbarReset` を実装します。

    > [!NOTE]
    > アプリケーションの起動中にツール バーが初期化されたとき、またはカスタマイズ中にツール バーがリセットされたときに、フレームワークはこのメッセージをメイン フレーム ウィンドウに送信します。 どちらの場合も、標準のツールバーボタンをカスタムの [ **検索** ] コンボボックスボタンに置き換える必要があります。

1. ハンドラーで、 `AFX_WM_RESETTOOLBAR` ツールバー ID、つまり AFX_WM_RESETTOOLBAR メッセージの *WPARAM* を調べます。 ツールバー ID が [ **検索** ] コンボボックスボタンを含むツールバーの ID と同じ場合は、 [Cmfctoolbar:: replacebutton](../mfc/reference/cmfctoolbar-class.md#replacebutton) を呼び出して、 **検索** ボタン (コマンド ID を持つボタン) を `ID_EDIT_FIND)` オブジェクトで置き換え `CFindComboButton` ます。

    > [!NOTE]
    > `CFindComboBox` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックで `ReplaceButton` オブジェクトを作成できます。

### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>[カスタマイズ] ダイアログ ボックスへの Find コントロールの追加

カスタマイズハンドラーで `OnViewCustomize` 、 [Cmfctoolbarscustomizedialog:: replacebutton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) を呼び出して、[ **検索** ] ボタン (コマンド ID を持つボタン `ID_EDIT_FIND` ) をオブジェクトに置き換え `CFindComboButton` ます。

## <a name="see-also"></a>関連項目

[階層図](../mfc/hierarchy-chart.md)<br/>
[Classes](../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBar クラス](../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarButton クラス](../mfc/reference/cmfctoolbarbutton-class.md)<br/>
[CMFCToolBarComboBoxButton クラス](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)<br/>
[CMFCToolBarsCustomizeDialog クラス](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
