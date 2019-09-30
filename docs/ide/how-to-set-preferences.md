---
title: Visual Studio C++でコーディング設定を設定する
ms.description: Customize C++ formatting, colors, layout, line numbers, menus and more in the Visual Studio IDE.
ms.topic: overview
ms.date: 09/27/2019
ms.openlocfilehash: 90c9f39135b90a2c5015861a78dd8760b9a8aeed
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686948"
---
# <a name="set-your-c-coding-preferences-in-visual-studio"></a>Visual Studio C++でコーディング設定を設定する

Visual Studio をカスタマイズC++することにより、コーディングエクスペリエンスをより使いやすく、生産性と pleasurable を高めることができます。 メニューやツールバーをカスタマイズしたり、ウィンドウのレイアウトを調整したり、配色C++テーマを設定したり、さまざまな種類の ClangFormat を含む書式設定規則を指定したり、カスタムキーボードショートカットを作成したりできます。 複数のコンピューター間で設定を同期し、複数の設定セットを作成して保存し、チームメイトと共有できます。 追加のカスタム動作を提供する Visual Studio Marketplace から拡張機能をインストールすることができます。 これらのオプションの多くは[、「Visual STUDIO IDE のカスタマイズ](/visualstudio/ide/personalizing-the-visual-studio-ide)」に記載されています。

## <a name="arrange-window-layout"></a>ウィンドウレイアウトの配置

Visual Studio ウィンドウ内では、領域はメインメニュー、ツールバー、コードエディター (またはドキュメントウィンドウ)、およびツールウィンドウ (**ソリューションエクスプローラー**、**エラー一覧**など) に分割されます。 一部のウィンドウは、同じ位置に重なっています。 たとえば、**ソリューションエクスプローラー**、**クラスビュー**、**リソースビュー**、**ソース管理エクスプローラー**はすべて同じ既定の位置を共有します。 これらを切り替えるには、フレームの下部にあるタブをクリックします。 これらのウィンドウのうち2つ以上を同時に表示するには、そのうちの1つをタイトルバーで新しい位置にドラッグするだけです。 これは、Visual Studio のメインウィンドウの境界の1つに対してドッキングするか、フローティングすることができます。 次の図は、既定の位置からコードエディターの左側の新しいドッキング位置にドラッグするプロセスの**チームエクスプローラー**ウィンドウを示しています。 青い網掛け領域は、マウスボタンが離されたときにウィンドウが配置される場所を示しています。

![ウィンドウレイアウトの変更](media/window-layout-move-team-explorer.png)

ドキュメントウィンドウでは、開いている各ファイルがタブ付きフレームに含まれています。 ツールウィンドウと同様に、これらのタブをフローティングまたはロックできます。 詳細については、「[Visual Studio のウィンドウ レイアウトをカスタマイズする](/visualstudio/ide/customizing-window-layouts-in-visual-studio)」を参照してください。

すべてのツールウィンドウを非表示にして、コードエディターウィンドウを最大化するには、 **Alt**キーを押し  + **Shift**@no__t を押して、*全画面表示モード***を切り替え**ます。

## <a name="set-c-coding-styles-and-formatting"></a>コーディングC++スタイルと書式設定の設定

インデントや中かっこの位置など、多くの個別のコード書式設定オプションを指定するには、**ツール** > **オプション** > **テキストエディター** > **C/C++**  >  の**書式設定**(または型**Ctrl + Q を押し**て、"書式設定" を検索します)。 また、 [Clangformat](https://clang.llvm.org/docs/ClangFormat.html)スタイル (または独自のカスタム clangformat スタイル) のいずれかを指定することもできます。

![ClangFormat オプション](media/clang-format-ide.png)

すべての書式設定オプションの詳細については、「[[オプション]、C++[テキストエディター]、[C/]、[書式設定](/visualstudio/ide/reference/options-text-editor-c-cpp-formatting)]」を参照してください。

## <a name="set-the-color-theme"></a>配色テーマの設定

明るい背景または暗い背景を設定するには、 **Ctrl + Q キーを押し**て、"配色テーマ" を検索します。 また、**ツール** > **オプション** > **環境**で、 **[配色テーマ]** を選択して入手することもできます。

![配色テーマ](media/tools-options-color-theme.png)

次の図は、ダークテーマを示しています。

![ダーク テーマ](media/tools-options-dark-theme.png)

## <a name="customize-code-colorization"></a>コードの色付けをカスタマイズする

Visual Studio 2019 では、コード要素をエディターで色付けする方法を指定する3つの定義済み*配色*から選択できます。 テーマを選択するには、 **[ツール**@no__t-**1 オプション** > **テキストエディター**]  > **C/C++**  > **ビュー**を選択し、 **[配色]** を選択します。

![C++配色](media/color-schemes.png)

**Visual Studio 2017**配色では、ほとんどのコード要素は単に黒です。 **強化**された配色では、関数、ローカル変数、マクロ、およびその他の要素が色分けされています。 @No__t 0Enhanced (Globals およびメンバー) @no__t 0 のスキーム、グローバル関数と変数は、クラスメンバーとは対照的に色分けされています。 既定のモードは**拡張**され、次のようになります。

![強化された配色](media/color-scheme-enhanced.png)

アクティブになっているテーマまたは配色に関係なく、個々のコード要素のフォントと色をカスタマイズするには、[**ツール** > **オプション]**  > **環境** > **フォントおよび色**(または [種類 **]) に移動します。Ctrl + Q を押し**て、"Fonts" を検索します)。 次のオプションがC++表示されるまで、表示項目の一覧を下にスクロールします。

![C++フォントおよび色のオプション](media/tools-options-cpp-colors.png)

ここで設定した色は、配色に対して定義されている値よりも優先されます。 色を変更して、配色に既定の色を使用する場合は、**既定値**に戻す必要があります。

## <a name="customize-the-toolbars"></a>ツールバーのカスタマイズ

ツールバーには、メニューやキーボードショートカットを使用するのではなく、1回のマウスクリックでコマンドを発行する便利な方法が用意されています。 Visual Studio には、ツールバーの標準セットが含まれています。 標準的C++な開発では、最も役に立つツールバーは、通常、標準、テキストエディター、ビルド、デバッグ、ソース管理、および場合によってはファイルを比較することができます。 Windows 開発の場合は、ダイアログエディターとイメージエディターを使用して、ダイアログと編集アイコンをレイアウトすることができます。

ツールバーのアイコンの上にマウスを移動すると、表示されるコマンドが表示されます。

![ツールバーのクイックヒント](media/toolbar-mouse-hover.png)

下矢印をクリックすると、コマンドを追加または削除したり、カスタムツールバーを作成したりできます。 ツールバーを新しい場所に移動するには、左側の点線のバーでドラッグします。

![ツールバーのカスタマイズまたは移動](media/toolbar-move-edit.png).

詳細については、「[方法 :Visual Studio @ no__t でメニューとツールバーをカスタマイズします。

## <a name="show-or-hide-line-numbers"></a>行番号の表示と非表示を切り替えます

エディターウィンドウの左側に行番号を表示するかどうかを指定するには、**行**番号に移動し、チェックボックスをオンまたはオフにします。

![[行番号]](media/tools-options-line-numbers.png)

## <a name="create-keyboard-shortcuts"></a>ショートカットキーの作成

Visual Studio のすべてのコマンドは、Ctrl、Alt、Shift キーを使用して、キーのさまざまな組み合わせを使用したキーボードショートカットで作成できます。 独自のショートカットを作成するには、 **[ツール]**  > **オプション** > **環境** > **キーボード**の順に移動します (または**Ctrl + Q キーを押し**て、"ショートカット" を検索します)。 詳細については、「 [Visual Studio でのキーボードショートカットの識別とカスタマイズ](/visualstudio/ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio)」を参照してください。
