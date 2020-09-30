---
title: C++ コードをアップグレードするための Visual Studio IDE ツール
description: C++ コードエディターと Visual Studio のコード分析ツールは、C++ コードベースを最新化するのに役立ちます。
ms.date: 11/13/2019
ms.topic: conceptual
ms.openlocfilehash: d6368445d16232ff968b7116b0f0313e97aa144c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503758"
---
# <a name="visual-studio-ide-tools-for-upgrading-c-code"></a>C++ コードをアップグレードするための Visual Studio IDE ツール

Visual Studio を使用すると、コンパイラオプション、コード分析の警告、およびエディターの機能 (クイック修正、クイックヒント、強化されたスクロールバーなど) を使用して、従来の C++ コードをアップグレードできます。 "レガシコード" という用語は、次のいずれかのカテゴリを指します。

- 以前は Microsoft C++ コンパイラ (MSVC) によって許可されていたが、C++ 標準に準拠していないコード。

   以前の準拠していない MSVC コードをアップグレードするには、 [/permissive-](../build/reference/permissive-standards-conformance.md) コンパイラオプションをオンにします。 コードエディターでは、準拠していない使用状況のすべてのインスタンスに赤い波線が付きます。 [ **エラー一覧** ] ウィンドウのエラーメッセージには、エラーの修正方法に関する推奨事項が含まれています。 エラーコードをクリックして、ドキュメントのヘルプページにアクセスします。 一度にすべてのエラーを修正するのは現実的ではありません。非準拠コードを段階的にアップグレードするには、 **寛容** オプションをオンにし、いくつかのエラーを修正してから、もう一度オプションをオフにします。 このコードは、新しい機能強化を使用してコンパイルされ、後で残りの問題を修正することができます。 準拠していない MSVC コードの例については、 [/permissive-](../build/reference/permissive-standards-conformance.md) のページを参照してください。

- 以前のバージョンの C++ 標準で許可されていたコードが、今後のバージョンでは非推奨または削除されています。

   新しい言語標準にアップグレードするには、 [C++ Language standard](../build/reference/std-specify-language-standard-version.md) オプションを目的の標準に設定し、発生したコンパイルエラーを修正します。 一般に、言語標準を [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)に設定することをお勧めします。 新しい標準にアップグレードするときに発生するエラーは、 **寛容** オプションを使用した場合に発生するエラーとは関係ありません。

- 標準のすべてのバージョンに準拠しているが、最新の C++ でのベストプラクティスとは見なされないコード。

   変更が推奨されるコードを特定するには、 [コード分析](../code-quality/code-analysis-for-c-cpp-overview.md)を実行します。

## <a name="open-and-convert-a-legacy-project"></a>レガシプロジェクトを開いて変換する

レガシプロジェクトが以前のバージョンの Visual Studio に基づいている場合は、Visual Studio 2017 または Visual Studio 2019 で開くことができます。 Visual Studio は、最新のコンパイラと IDE のすべての機能をサポートするように、現在のプロジェクトスキーマに自動的に変換します。

![プロジェクトをアップグレードする](media/upgrade-dialog-v142.png "プロジェクトをアップグレードする")

詳細については、「 [以前のバージョンの Visual Studio から C++ プロジェクトをアップグレード](upgrading-projects-from-earlier-versions-of-visual-cpp.md)する」を参照してください。

## <a name="search-the-code-base"></a>コードベースの検索

コードベースのアップグレードでは、多くの場合、複数のファイルを検索する必要があります。 コードベース内の何かを検索するには、Ctrl キーを押し **ながら T** キーを押して、[すべての検索] ボックス **に移動** します。

![すべてにジャンプ](media/go-to-all.png "すべてにジャンプ")

検索範囲を絞り込むには、1文字のフィルターの1つを入力し、その後にスペースを入力して、探しているものを入力します。

## <a name="error-list"></a>エラー一覧

目的の C++ 言語標準およびその他のコンパイラオプション (**プロジェクト**  >  **プロパティ**  >  **全般**) を設定したら、 **Ctrl + Shift + B**キーを押してプロジェクトをコンパイルします。 コード内のさまざまな場所に赤い波線の形式でエラーと警告が表示されることが予想されます。 エラーは、 **エラー一覧**にも表示されます。 特定のエラーの詳細については、エラーコードをクリックして、ドキュメントのヘルプページにアクセスしてください。 "C" で始まるエラーコードはコンパイラエラーです。 "MSB" で始まるコードは、プロジェクト構成に問題があることを示す MSBuild エラーです。

![エラー一覧でのコンパイラおよび MSBuild エラー](media/compiler-error-list.png "エラー一覧でのコンパイラおよび MSBuild エラー")

## <a name="document-health-indicator"></a>ドキュメントの正常性インジケーター

エディターの下部にある [ドキュメントのヘルス] インジケーターには、現在のドキュメントのエラーと警告の数が表示されます。これにより、警告/エラーの間を直接移動することができます。

![ドキュメントのヘルスインジケーター](media/document-health-indicator.png "ドキュメントのヘルスインジケーター")

多くの場合、Visual Studio の変更履歴と準拠の改善に関するドキュメントで、特定のエラーに関する詳細情報を確認できます。

- [C++ 準拠の強化](../overview/cpp-conformance-improvements.md)
- [Visual C++ の変更履歴 2003-2015](visual-cpp-change-history-2003-2015.md)
- [アップグレード時の潜在的な問題の概要](overview-of-potential-upgrade-issues-visual-cpp.md)

## <a name="use-code-analysis-to-modernize-your-code"></a>コード分析を使用してコードを最新化する

アップグレード時には、プロジェクトに対してコード分析を実行することをお勧めします。コードは、少なくとも Microsoft ネイティブ推奨規則に準拠している必要があります。 これらのルールは、Microsoft によって定義されたルールと、 [C++ Core Guidelines](https://isocpp.github.io/CppCoreGuidelines/CppCoreGuidelines)のサブセットの組み合わせです。 これらに準拠することで、一般的なバグのソースを大幅に削減または排除し、同時にコードを読みやすくし、保守が容易になります。 Microsoft ネイティブ推奨規則を使用したコード分析は、既定で有効になっています。 [**プロジェクト**  >  の**プロパティ**] [  >  **コード分析**] で、追加のルールを有効にすることができます。 ルールのいずれかに違反しているコードは、警告としてフラグが設定され、コードエディターで緑の波線で下線が引かれます。 波線の上にマウスポインターを置くと、問題を説明する **クイック** ヒントが表示されます。

![コード分析ツールヒント](media/code-analysis-tooltip.png "コード分析の警告")

[ **コード** ] 列のフィルターアイコンをクリックして、表示する警告を選択します。

![エラー一覧でのコード分析フィルター](media/code-analysis-filter.png "エラー一覧でのコード分析フィルター")

コード分析のエラーと警告は、コンパイラエラーと同様に **エラー一覧** にも表示されます。

![エラー一覧でのコード分析の警告](media/code-analysis-error-list.png "エラー一覧でのコード分析の警告")

アクティブになっている規則を変更し、カスタムのルールセットを作成できます。 コード分析の使用方法の詳細については、「 [C/c + + のコード分析の概要](../code-quality/code-analysis-for-c-cpp-overview.md)」を参照してください。

## <a name="use-quick-actions-to-modernize-code"></a>クイックアクションを使用してコードを最新化する

コードエディターには、いくつかの一般的な推奨事項に関するクイックアクションが用意されています。 電球アイコンが表示されている場合は、それをクリックすると、使用可能なクイックアクションを確認できます。

### <a name="convert-macros-to-constexpr-functions"></a>マクロを constexpr 関数に変換する

次の図は、というマクロの使用方法を示してい `AVERAGE` ます。これには既定のセマンティックカラーが含まれています。 この画像には、マウスカーソルが上に置かれたときに表示される QuickInfo ツールヒントも表示されます。

![QuickInfo マクロの展開](media/macro-expansion-quick-info.png "QuickInfo ツールヒントマクロの展開")

最新の C++ ではマクロを使用しないことをお勧めします。 Visual Studio では、マクロを関数に簡単に変換できるようになり **`constexpr`** ます。

1. を右クリック `AVERAGE` し、[ **定義へのジャンプ**] を選択します。
2. [ドライバー] アイコンをクリックし、[**マクロを constexpr に変換**] を選択します。

   ![クイックアクションマクロから constexpr へ](media/quick-action-macro-to-constexpr.png "クイックアクションマクロから constexpr へ")

マクロは次のように変換されます。

![constexpr 関数](media/constexpr-function.png "constexpr 関数")

また、への呼び出し `AVERAGE` は関数呼び出しとして色分けされており、クイックツールヒントは関数の推測された型を示しています。

![constexpr 関数呼び出し](media/constexpr-function-call.png "constexpr 関数呼び出し")

### <a name="initialize-variables"></a>変数の初期化

初期化されていない変数は、重大なバグにつながるランダムな値を保持できます。 コード分析でこれらのインスタンスにフラグを使用すると、エディターはクイックアクションを提供します。

![変数を初期化する](media/init-variable.png "変数の初期化クイックアクション")

### <a name="convert-to-raw-string-literal"></a>生文字列に変換

未加工の文字列リテラルは、エスケープ文字が埋め込まれている文字列よりもエラーが発生しやすく、便利ではありません。 文字列を右クリックし、[ **クイックアクション** ] を選択して、未加工の文字列リテラルに変換します。

![未加工の文字列リテラル](media/raw-string-literal.png "未加工の文字列リテラル")

文字列はに変換され `R"(C:\Users\bjarnes\demo\output.txt)"` ます。
