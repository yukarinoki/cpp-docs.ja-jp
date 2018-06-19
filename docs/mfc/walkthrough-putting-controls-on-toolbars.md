---
title: 'チュートリアル: ツールバーへのコントロールを配置する |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Customize dialog box, adding controls
- toolbars [MFC], adding controls
ms.assetid: 8fc94bdf-0da7-45d9-8bc4-52b7b1edf205
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c134431500ed3e7b2b2229ea5b4b3da7cac6fa48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385084"
---
# <a name="walkthrough-putting-controls-on-toolbars"></a>チュートリアル: ツール バーへのコントロールの追加
このトピックでは、Windows コントロールを含むツール バー ボタンをツール バーに追加する方法を説明します。 MFC では、ツールバーのボタンがある必要があります、 [CMFCToolBarButton クラス](../mfc/reference/cmfctoolbarbutton-class.md)-たとえば、クラスを派生[CMFCToolBarComboBoxButton クラス](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)、 [CMFCToolBarEditBoxButton クラス](../mfc/reference/cmfctoolbareditboxbutton-class.md)、[CMFCDropDownToolbarButton クラス](../mfc/reference/cmfcdropdowntoolbarbutton-class.md)、または[CMFCToolBarMenuButton クラス](../mfc/reference/cmfctoolbarmenubutton-class.md)です。  
  
## <a name="adding-controls-to-toolbars"></a>ツール バーへのコントロールの追加  
 ツール バーにコントロールを追加するには、次の手順を実行します。  
  
1.  親ツール バー リソースでボタンのダミー リソース ID を予約します。 Visual Studio のツール バー エディターを使用してボタンを作成する方法の詳細については、次を参照してください。、[ツール バー エディター](../windows/toolbar-editor.md)トピックです。  
  
2.  親ツール バーのすべてのビットマップでボタンのツール バー イメージ (ボタン アイコン) を予約します。  
  
3.  `AFX_WM_RESETTOOLBAR` メッセージを処理するメッセージ ハンドラーで、次の操作を行います。  
  
    1.  `CMFCToolbarButton` 派生クラスを使用して、ボタン コントロールを作成します。  
  
    2.  ダミーのボタンを使用して、新しいコントロールを置き換える[CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton)です。 `ReplaceButton` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックでボタン オブジェクトを作成できます。  
  
> [!NOTE]
>  アプリケーションのカスタマイズを有効にした場合を使用して、ツールバーをリセットする必要があります、**リセット**のボタンでは、**ツールバー**のタブ、**カスタマイズ** ダイアログ ボックスを表示する、再コンパイルした後、アプリケーションでコントロールを更新します。 ツール バーの状態は Windows レジストリに保存され、アプリケーションの起動中に `ReplaceButton` メソッドが実行された後、レジストリ情報が読み込まれ適用されます。  
  
## <a name="toolbar-controls-and-customization"></a>ツール バー コントロールとカスタマイズ  
 **コマンド**のタブ、**カスタマイズ** ダイアログ ボックスに、アプリケーションで使用できるコマンドの一覧が含まれています。 既定では、**カスタマイズ** ダイアログ ボックスは、アプリケーションのメニューを処理し、各メニュー カテゴリで標準ツール バー ボタンのリストを構築します。 ツール バー コントロールで提供される拡張機能を保持するでカスタム コントロールを備えた標準ツール バー ボタンを置き換える必要があります、**カスタマイズ** ダイアログ ボックス。  
  
 作成するカスタマイズを有効にすると、**カスタマイズ** ダイアログ ボックスで、カスタマイズ ハンドラー`OnViewCustomize`を使用して、 [CMFCToolBarsCustomizeDialog クラス](../mfc/reference/cmfctoolbarscustomizedialog-class.md)クラスです。 表示する前に、**カスタマイズ** ダイアログ ボックスを呼び出して[CMFCToolBarsCustomizeDialog::Create](../mfc/reference/cmfctoolbarscustomizedialog-class.md#create)、呼び出す[CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)を置き換える新しいコントロールに標準のボタンです。  
  
## <a name="example-creating-a-find-combo-box"></a>例 : [Find] コンボ ボックスの作成  
 ここでは、`Find` コンボ ボックスを作成する方法について説明します。このコンボ ボックスはツール バーに表示され、最近使用した検索文字列が表示されます。 ユーザーはコントロールに文字列を入力した後、Enter キーを押してドキュメントを検索するか、Esc キーを押してフォーカスをメイン フレームに戻します。 この例でドキュメントが表示されている、 [CEditView クラス](../mfc/reference/ceditview-class.md)-ビューを派生します。  
  
### <a name="creating-the-find-control"></a>Find コントロールの作成  
 まず、`Find` コンボ ボックス コントロールを作成します。  
  
1.  アプリケーション リソースにボタンとコマンドを追加します。  
  
    1.  アプリケーション リソースで、`ID_EDIT_FIND` コマンド ID を持つ新しいボタンをアプリケーションのツール バー、およびツール バーに関連付けられたビットマップに追加します。  
  
    2.  ID_EDIT_FIND コマンド ID を使用して新しいメニュー項目を作成します。  
  
    3.  新しい文字列 "Find the text\nFind" を文字列テーブルに追加し、`ID_EDIT_FIND_COMBO` コマンド ID を割り当てます。 この ID は、`Find` コンボ ボックスのコマンド ID として使用されます。  
  
        > [!NOTE]
        >  `ID_EDIT_FIND` は `CEditView` によって処理される標準のコマンドであるため、このコマンド用の特別なハンドラーを実装する必要はありません。  ただし、新しいコマンド `ID_EDIT_FIND_COMBO` のハンドラーを実装する必要があります。  
  
2.  新しいクラスを作成`CFindComboBox`から派生した[CComboBox クラス](../mfc/reference/ccombobox-class.md)です。  
  
3.  `CFindComboBox` クラスで、`PreTranslateMessage` 仮想メソッドをオーバーライドします。 このメソッドは、処理するコンボ ボックスを有効になります、 [WM_KEYDOWN](http://msdn.microsoft.com/library/windows/desktop/ms646280)メッセージ。 ユーザーが Esc キーを押す (`VK_ESCAPE`) と、フォーカスがメイン フレーム ウィンドウに戻ります。 ユーザーが Enter キーを押す (`VK_ENTER`) と、`WM_COMMAND` コマンド ID を含む `ID_EDIT_FIND_COMBO` メッセージがメイン フレーム ウィンドウにポストされます。  
  
4.  クラスを作成、`Find`コンボ ボックス ボタンから派生した[CMFCToolBarComboBoxButton クラス](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)です。 この例では、 `CFindComboButton`という名前が付いています。  
  
5.  `CMFCToolbarComboBoxButton` のコンストラクターは、3 つのパラメーター (ボタンのコマンド ID、ボタン イメージのインデックス、およびコンボ ボックスのスタイル) を受け取ります。 これらのパラメーターを次のように設定します。  
  
    1.  `ID_EDIT_FIND_COMBO` をコマンド ID として渡します。  
  
    2.  使用して[CCommandManager::GetCmdImage](http://msdn.microsoft.com/en-us/4094d08e-de74-4398-a483-76d27a742dca)で`ID_EDIT_FIND`イメージ インデックスを取得します。  
  
    3.  使用可能なコンボ ボックス スタイルの一覧は、次を参照してください。[コンボ ボックス スタイル](../mfc/reference/styles-used-by-mfc.md#combo-box-styles)です。  
  
6.  `CFindComboButton` クラスで、`CMFCToolbarComboBoxButton::CreateCombo` メソッドをオーバーライドします。 ここで、`CFindComboButton` オブジェクトを作成し、オブジェクトへのポインターを返す必要があります。  
  
7.  使用して、 [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial)コンボ ボタンを固定するマクロです。 ワークスペース マネージャーは、ボタンの状態を自動的に読み込み、Windows レジストリに保存します。  
  
8.  ドキュメント ビューで `ID_EDIT_FIND_COMBO` ハンドラーを実装します。 使用して[CMFCToolBar::GetCommandButtons](../mfc/reference/cmfctoolbar-class.md#getcommandbuttons)で`ID_EDIT_FIND_COMBO`をすべて取得する`Find`コンボ ボックス ボタンです。 カスタマイズにより、同じコマンド ID を持つ複数のボタンが存在する可能性があります。  
  
9. ID_EDIT_FIND メッセージ ハンドラーで`OnFind`を使用して[CMFCToolBar::IsLastCommandFromButton](../mfc/reference/cmfctoolbar-class.md#islastcommandfrombutton)から検索 コマンドが送信されたかどうかを決定する、`Find`コンボ ボックス ボタンをクリックします。 該当する場合は、テキストを検索し、検索文字列をコンボ ボックスに追加します。  
  
### <a name="adding-the-find-control-to-the-main-toolbar"></a>メイン ツール バーへの Find コントロールの追加  
 ツール バーにコンボ ボックス ボタンを追加するには、次の手順を実行します。  
  
1.  メイン フレーム ウィンドウに `AFX_WM_RESETTOOLBAR` メッセージ ハンドラー `OnToolbarReset` を実装します。  
  
    > [!NOTE]
    >  アプリケーションの起動中にツール バーが初期化されたとき、またはカスタマイズ中にツール バーがリセットされたときに、フレームワークはこのメッセージをメイン フレーム ウィンドウに送信します。 どちらの場合も、標準のツール バー ボタンをカスタム `Find` コンボ ボックス ボタンに置き換える必要があります。  
  
2.  `AFX_WM_RESETTOOLBAR` ハンドラーで、ツール バー ID、つまり `WPARAM` メッセージの `AFX_WM_RESETTOOLBAR` を確認します。 ツールバー ID が含まれているツールバーのものと等しい場合、`Find`コンボ ボックス ボタン、呼び出し[CMFCToolBar::ReplaceButton](../mfc/reference/cmfctoolbar-class.md#replacebutton)を置き換える、`Find`ボタン (コマンド ID を持つボタンは、`ID_EDIT_FIND)`で、`CFindComboButton`オブジェクト。  
  
    > [!NOTE]
    >  `CFindComboBox` はボタン オブジェクトをコピーしてそのコピーを保持するため、開発者はスタックで `ReplaceButton` オブジェクトを作成できます。  
  
### <a name="adding-the-find-control-to-the-customize-dialog-box"></a>[カスタマイズ] ダイアログ ボックスへの Find コントロールの追加  
 カスタマイズ ハンドラーで`OnViewCustomize`、呼び出す[CMFCToolBarsCustomizeDialog::ReplaceButton](../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton)を置き換える、`Find`ボタン (コマンド ID を持つボタンは、`ID_EDIT_FIND)`で、`CFindComboButton`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../mfc/hierarchy-chart.md)   
 [クラス](../mfc/reference/mfc-classes.md)   
 [CMFCToolBar クラス](../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton クラス](../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton クラス](../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCToolBarsCustomizeDialog クラス](../mfc/reference/cmfctoolbarscustomizedialog-class.md)
