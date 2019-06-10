---
title: コードの作成とリファクタリング (C++)
description: Visual Studio の C++ コード エディターを使用して、コードの書式設定、移動、理解、リファクタリングを行います。
ms.date: 05/14/2019
ms.assetid: 56ffb9e9-514f-41f4-a3cf-fd9ce2daf3b6
ms.openlocfilehash: 04f738cd6fdd456c432c334df42f37339e7fa49e
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "66182632"
---
# <a name="writing-and-refactoring-code-c"></a>コードの作成とリファクタリング (C++)

C++ コード エディターと Visual Studio IDE ではコーディングの補助機能の多くが提供されています。 いくつかは C++ に固有で、いくつかは基本的にすべての Visual Studio の言語と同じです。 共有機能の詳細については、[コード エディターとテキスト エディターでのコードの記述](/visualstudio/ide/writing-code-in-the-code-and-text-editor)に関するページを参照してください。 C++ 固有の機能を有効にして構成するためのオプションは、 **[ツール] &#124; [オプション] &#124; [テキスト エディター] &#124; [C/C++]** にあります。 設定するオプションを選択した後、ダイアログにフォーカスがあるときに **F1** キーを押すと、詳細なヘルプを表示できます。 コードの一般的な書式設定オプションを確認するには、 **[クイック起動]** に「`Editor C++`」と入力します。

将来のバージョンの Visual Studio に含まれる場合とそうでない場合がある実験用の機能は、[[テキスト エディター]、[C++]、[実験用]](/visualstudio/ide/reference/options-text-editor-c-cpp-experimental) ダイアログにあります。 Visual Studio 2017 では、このダイアログで**予測 IntelliSense** を有効にすることができます。

## <a name="adding-new-files"></a>新しいファイルの追加

プロジェクトに新しいファイルを追加するには、ソリューション エクスプローラーでプロジェクト ノードを右クリックし、 **[追加] &#124; [新規作成]** を選択します。

## <a name="formatting-options"></a>書式設定オプション

インデント、中かっこの補完、色表示などの書式設定オプションを設定するには、 **[クイック起動]** ウィンドウに「C++ Formatting」と入力します。 Visual Studio 2017 バージョン 15.7 以降では、ClangFormat がサポートされています。 **[ツール] &#124; [オプション] &#124; [テキスト エディター] &#124; [C/C++] &#124; [書式設定]** の [C/C++ 書式設定プロパティ ページ](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting)で構成することができます。

![C++ 書式設定オプション](media/cpp-formatting-options.png)

## <a name="intellisense"></a>IntelliSense

IntelliSense は、メンバー、種類、および関数のオーバーロードについてのインラインの情報を提供する一連の機能の名前です。 入力すると表示されるメンバー リスト ボックスを次の図に示します。 Tab キーを押すと、コード ファイルに、選択した項目のテキストを入力することができます。

![C&#43;&#43; のメンバー リスト ドロップダウン](../ide/media/vs2015_cpp_statement_completion.png "vs2015_cpp_statement_completion")

完全な情報は、「[Visual C++ IntelliSense](/visualstudio/ide/visual-cpp-intellisense)」を参照してください。

## <a name="insert-snippets"></a>スニペットの挿入

スニペットは、定義済みのソース コードです。 単一のポイント、選択したテキストの上で右クリックすると、スニペットを挿入するか、選択したテキストをスニペットで囲みます。 次の図は、for ループで選択したステートメントを囲む 3 つの手順を示します。 最終的なイメージの黄色のハイライトは、Tab キーでアクセスできる編集可能なフィールドです。 詳細については、「[Code Snippets](/visualstudio/ide/code-snippets)」を参照してください。

![Visual C&#43;&#43; のスニペットの挿入ドロップダウン](../ide/media/vs2015_cpp_surround_with.png "vs2015_cpp_surround_with")

## <a name="add-class"></a>クラスの追加

クラス ウィザードを使用して、新しいクラスを **[プロジェクト]** メニューから追加します。

![Visual C&#43;&#43; での新しいクラスの追加](../ide/media/vs2015_cpp_add_class.png "vs2015_cpp_add_class")

クラス ウィザードを使用して、既存のクラスを変更したり、調べたりすることもできます。

![Visual C&#43;&#43; のクラス ウィザード](../ide/media/vs2015_cpp_class_wizard.png "vs2015_cpp_class_wizard")

詳細については、「[コード ウィザードを使用した機能の追加 (C++)](../ide/adding-functionality-with-code-wizards-cpp.md)」を参照してください。

## <a name="refactoring"></a>リファクタリング

クイック操作のコンテキスト メニューから、またはエディターの[電球](/visualstudio/ide/perform-quick-actions-with-light-bulbs)をクリックすることで、リファクタリングが利用できます。  **[編集]、[リファクター]** メニューから利用できるものもあります。  これには次の機能があります。

* [名前の変更](refactoring/rename.md)
* [Extract 関数](refactoring/extract-function.md)
* [純粋仮想の実装](refactoring/implement-pure-virtuals.md)
* [宣言/定義の作成](refactoring/create-declaration-definition.md)
* [Move 関数の定義](refactoring/move-definition-location.md)
* [未加工の文字列リテラルに変換](refactoring/convert-to-raw-string-literal.md)
* [署名の変更](refactoring/change-signature.md)

## <a name="navigate-and-understand"></a>移動して理解する

Visual C++ では、他の言語と多くのコード ナビゲーション機能を共有します。 詳細については、「[コード間の移動](/visualstudio/ide/navigating-code)」と[コードの構造の表示](/visualstudio/ide/viewing-the-structure-of-code)に関するページを参照してください。

## <a name="quickinfo"></a>QuickInfo

変数上にカーソルを置き、型情報を表示します。

![Visual C&#43;&#43; のクイックヒント](../ide/media/vs2015_cpp_quickinfo.png "vs2015_cpp_quickInfo")

## <a name="open-document-navigate-to-header"></a>ドキュメントを開く (ヘッダーに移動)

`#include` ディレクティブでヘッダー名を右クリックして、ヘッダー ファイルを開きます。

![Visual C&#43;&#43; の [ドキュメントを開く] メニュー オプション](../ide/media/vs2015_cpp_open_document.png "vs2015_cpp_open_document")

## <a name="peek-definition"></a>定義をここに表示

変数または関数宣言の上にカーソルを置き、右クリックして **[ピークの定義]** を選択し、その定義のインライン ビューを表示します。 詳細については、[[定義をここに表示] (Alt + F12)](/visualstudio/ide/how-to-view-and-edit-code-by-using-peek-definition-alt-plus-f12) に関するページを参照してください。

![Visual C&#43;&#43; の [定義をここに表示]](../ide/media/vs2015_cpp_peek_definition.png "vs2015_cpp_peek_definition")

## <a name="go-to-definition"></a>[定義へ移動]

変数または関数宣言の上にカーソルを置き、右クリックして **[定義へ移動]** を選択し、オブジェクトが定義されているドキュメントを開きます。

## <a name="view-call-hierarchy"></a>呼び出し階層の表示

関数呼び出しを右クリックし、呼び出すすべての関数、および呼び出されるすべての関数の再帰的な一覧を表示します。 一覧内の各関数は、同じ方法で展開できます。 詳細については、[呼び出し階層](/visualstudio/ide/reference/call-hierarchy)に関するページを参照してください。

![Visual C&#43;&#43; の [呼び出し階層]](../ide/media/vs2015_cpp_call_hierarchy.png "vs2015_cpp_call_hierarchy")

## <a name="toggle-header--code-file"></a>ヘッダーの切り替え/コード ファイル

右クリックし、 **[ヘッダーの切り替え/コード ファイル]** を選択して、ヘッダー ファイルとその関連付けられたコード ファイルを切り替えます。

## <a name="outlining"></a>アウトライン

ソース コード ファイルの任意の場所を右クリックし、 **[アウトライン]** を選択して、定義やカスタムの領域を縮小または展開し、興味のある部分のみを簡単に参照できるようにします。 詳細については、「[アウトライン](/visualstudio/ide/outlining)」を参照してください。

![Visual C&#43;&#43; の [アウトライン]](../ide/media/vs2015_cpp_outlining.png "vs2015_cpp_outlining")

## <a name="scrollbar-map-mode"></a>スクロール バーのマップ モード

スクロール バーのマップ モードでは、実際には現在の場所を離れずに、迅速にスクロールしてコード ファイルを参照することができます。 または、コード マップ上の任意の場所をクリックして、その場所に直接移動します。 詳細については、「[方法 :スクロール バーをカスタマイズしてコードを追跡する](/visualstudio/ide/how-to-track-your-code-by-customizing-the-scrollbar)。

![Visual C&#43;&#43; のコード マップ](../ide/media/vs2015_cpp_code_map.png "vs2015_cpp_code_map")

## <a name="generate-graph-of-include-files"></a>インクルード ファイルのグラフを生成

プロジェクト内のコード ファイルを右クリックし、 **[インクルード ファイルのグラフを生成]** を選択して、他のファイルによって含まれているファイルのグラフを表示します。

![Visual C&#43;&#43; のインクルード ファイルのグラフ](../ide/media/vs2015_cpp_include_graph.png "vs2015_cpp_include_graph")

## <a name="f1-help"></a>F1 ヘルプ

任意の型、キーワード、または関数の上または直後にカーソルを置き、F1 キーを押して、docs.microsoft.com の関連するリファレンス トピックに直接移動します。 F1 は、エラー リストや多くのダイアログ ボックスの項目でも機能します。

## <a name="quick-launch"></a>クイック起動

Visual Studio の任意のウィンドウまたはツールを簡単に移動するには、UI の右上隅の [クイック起動] ウィンドウで、名前を入力します。 入力するにつれて、自動補完の一覧がフィルターされます。

![Visual Studio のクイック起動](../ide/media/vs2015_cpp_quick_launch.png "vs2015_cpp_quick_launch")
