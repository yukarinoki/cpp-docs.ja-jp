---
description: 詳細について:/Ob (関数のインライン展開)
title: /Ob (関数のインライン展開)
ms.date: 08/08/2019
f1_keywords:
- VC.Project.VCCLWCECompilerTool.InlineFunctionExpansion
- VC.Project.VCCLCompilerTool.InlineFunctionExpansion
- /ob
helpviewer_keywords:
- inline functions, function expansion compiler option [C++]
- -Ob1 compiler option [C++]
- -Ob0 compiler option [C++]
- /Ob0 compiler option [C++]
- /Ob1 compiler option [C++]
- any suitable compiler option [C++]
- Ob2 compiler option [C++]
- Ob1 compiler option [C++]
- /Ob2 compiler option [C++]
- Ob compiler option [C++]
- -Ob2 compiler option [C++]
- disable compiler option [C++]
- -Ob compiler option [C++]
- /Ob compiler option [C++]
- only __inline compiler option [C++]
- Ob0 compiler option [C++]
- inline expansion, compiler option
ms.assetid: f134e6df-e939-4980-a01d-47425dbc562a
ms.openlocfilehash: 9a003f83d27ca0517b427bab6f7ffda75ff51557
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214342"
---
# <a name="ob-inline-function-expansion"></a>/Ob (関数のインライン展開)

関数のインライン展開を制御します。 既定では、最適化すると、すべての関数に対するコンパイラの裁量によって拡張が行われます。これは、多くの場合、 *自動インライン展開* と呼ばれます。

## <a name="syntax"></a>構文

::: moniker range=">=msvc-160"

> **/Ob**{**0** | **1** | **2** | **3**}

::: moniker-end

::: moniker range="<=msvc-150"

> **/Ob**{**0** | **1** | **2**}

::: moniker-end

## <a name="arguments"></a>引数

**0**\
[/Od](od-disable-debug.md)の既定値。 インライン展開を無効にします。

**1**\
[Inline](../../cpp/inline-functions-cpp.md)、 [__inline](../../cpp/inline-functions-cpp.md)、または[__forceinline](../../cpp/inline-functions-cpp.md)とマークされた関数、またはクラス宣言で定義されている C++ メンバー関数の拡張のみを許可します。

**2**\
[/O1](o1-o2-minimize-size-maximize-speed.md)と[/O2](o1-o2-minimize-size-maximize-speed.md)の既定値。 インライン展開しないように明示的にマークされていない関数をコンパイラで拡張できるようにします。

::: moniker range=">=msvc-160"

**番**\
このオプションは、 **/ob2** よりも積極的なインライン展開を指定しますが、同じ制限があります。 **/Ob3** オプションは、Visual Studio 2019 以降で使用できます。

::: moniker-end

## <a name="remarks"></a>解説

インライン展開に関するオプションとキーワードは、インライン展開の対象となる候補をコンパイラに示すだけです。 関数がインラインで展開される保証はありません。 インライン展開を無効にすることはできますが、キーワードを使用している場合でも、特定の関数のインライン化をコンパイラに強制することはできません **`__forceinline`** 。

インライン展開の候補として関数を除外するには、 [__declspec (noinline)](../../cpp/noinline.md)、または [#pragma auto_inline (off)](../../preprocessor/auto-inline.md) と [#pragma auto_inline (on)](../../preprocessor/auto-inline.md) ディレクティブでマークされた領域を使用できます。 コンパイラにインライン展開ヒントを提供する別の方法については、「 [#pragma 組み込み](../../preprocessor/intrinsic.md) ディレクティブ」を参照してください。

> [!NOTE]
> プロファイリングテストの実行から収集された情報は、 **/Ob**、 **/os**、または **/ot** を指定したために適用される最適化よりも優先されます。 詳細については、「[ガイド付き最適化のプロファイル](../profile-guided-optimizations.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **最適化**] プロパティページを選択します。

1. **インライン関数の展開** プロパティを変更します。

::: moniker range=">=msvc-160"

**/Ob3** オプションは、[**インライン関数の展開**] プロパティでは使用できません。 設定する方法 **/ob3**:

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]** > **[C/C++]** > **[コマンド ライン]** プロパティ ページを選択します。

1. **追加のオプション** に「 **/ob3** 」と入力します。

::: moniker-end

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.InlineFunctionExpansion%2A>

## <a name="see-also"></a>関連項目

[/O オプション (コードの最適化)](o-options-optimize-code.md)\
[MSVC コンパイラオプション](compiler-options.md)\
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
