---
title: /analyze (コード分析)
description: Microsoft C++ コンパイラの/analyze オプションの構文と使用法。
ms.date: 07/27/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
ms.openlocfilehash: e970872e89132aed52190b8688f2cdaccab5ea6f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500081"
---
# <a name="analyze-code-analysis"></a>`/analyze` (コード分析)

コード分析とコントロール オプションを有効にします。

## <a name="syntax"></a>構文

::: moniker range=">=vs-2017"

> **`/analyze`**\
> **`/analyze-`**\
> **`/analyze:autolog`**\
> **`/analyze:autolog-`**\
> **`/analyze:autolog:ext`***拡張機能*\
> **`/analyze:log`***ファイル名*\
> **`/analyze:max_paths`***番号*\
> **`/analyze:only`**\
> **`/analyze:plugin`***プラグイン-dll*\
> **`/analyze:quiet`**\
> **`/analyze:ruleset`***ルールセット*\
> **`/analyze:stacksize`***番号*\
> **`/analyze:WX-`**

::: moniker-end
::: moniker range="vs-2015"

> **`/analyze`**\
> **`/analyze-`**\
> **`/analyze:autolog`**\
> **`/analyze:autolog-`**\
> **`/analyze:autolog:ext`***拡張機能*\
> **`/analyze:log`***ファイル名*\
> **`/analyze:max_paths`***番号*\
> **`/analyze:only`**\
> **`/analyze:plugin`***プラグイン-dll*\
> **`/analyze:quiet`**\
> **`/analyze:stacksize`***番号*\
> **`/analyze:WX-`**

::: moniker-end

## <a name="arguments"></a>引数

**`/analyze`**\
既定のモードで分析をオンにします。 分析出力は、他のエラーメッセージと同様に、コンソールまたは Visual Studio の **出力** ウィンドウに移動します。 **`/analyze-`** 分析を明示的にオフにするには、を使用します。

**`/analyze:autolog`**\
詳細なアナライザーの結果は、ソースファイルと同じ基本名との拡張子を持つファイルに XML として書き込まれ *`.pftlog`* ます。 **`/analyze:autolog-`** このログファイルを無効にします。

**`/analyze:autolog:ext`***拡張機能*\
詳細なアナライザーの結果は、ソースファイルと *拡張機能*の拡張機能と同じ基本名を持つファイルに XML として書き込まれます。

**`/analyze:log`***ファイル名*\
詳細なアナライザーの結果は、 *filename*によって指定されたファイルに XML として書き込まれます。

**`/analyze:max_paths`***番号*\
このオプションで使用される *number* パラメーターでは、分析するコードパスの最大数を指定します。 このパラメーターが指定されていない場合、既定では、数値は256です。 値を大きくすると、より詳細なチェックが行われますが、分析に時間がかかることがあります。

**`/analyze:only`**\
通常、コンパイラは、アナライザーを実行した後にコードを生成し、構文チェックをさらに実行します。 **`/analyze:only`** このオプションは、このコード生成パスをオフにします。 これにより、分析が高速になりますが、コンパイラのコード生成パスによって検出される可能性のあるコンパイラのエラーや警告は生成されません。 プログラムにコード生成エラーがない場合は、分析結果が信頼できない可能性があります。 このオプションを使用することをお勧めするのは、コードがエラーなしでコード生成構文チェックに合格した場合のみです。

**`/analyze:plugin`***プラグイン-dll*\
コード分析の実行の一部として、指定された PREfast プラグインを有効にします。

::: moniker range="<=vs-2017"

LocalEspC.dll は、C261XX 警告の範囲内で同時実行に関連するコード分析チェックを実装するプラグインです。 たとえば、 [C26100](../../code-quality/c26100.md)、 [C26101](../../code-quality/c26101.md)、  [C26167](../../code-quality/c26167.md)のようになります。

LocalEspC.dll を実行するには、次のコンパイラオプションを使用します。 **`/analyze:plugin LocalEspC.dll`**

::: moniker-end
::: moniker range=">=vs-2019"

ConcurrencyCheck.dll は、C261XX 警告の範囲内で同時実行に関連するコード分析チェックを実装します。 たとえば、 [C26100](../../code-quality/c26100.md)、 [C26101](../../code-quality/c26101.md)、  [C26167](../../code-quality/c26167.md)のようになります。

ConcurrencyCheck.dll を実行するには、まず開発者コマンドプロンプトから次のコマンドを実行します。

```cmd
set Esp.Extensions=ConcurrencyCheck.dll
```

その後、次のコンパイラオプションを使用します **`/analyze:plugin EspXEngine.dll`** 。

CppCoreCheck.dll を実行するには、まず開発者コマンドプロンプトから次のコマンドを実行します。

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

その後、次のコンパイラオプションを使用します **`/analyze:plugin EspXEngine.dll`** 。

::: moniker-end

**`/analyze:quiet`**\
アナライザーの出力をコンソールまたは Visual Studio の **出力** ウィンドウに表示しません。

::: moniker range=">=vs-2017"

**`/analyze:ruleset`***file_path。ルールセット*\
自分で作成できるカスタム規則セットなど、分析する規則セットを指定できます。 このスイッチを設定すると、ルールエンジンは、実行前に指定された規則セットの非メンバーを除外するため、より効率的になります。 それ以外の場合、エンジンはすべてのルールを確認します。

Visual Studio に付属するルールセットは、「」にあり *`%VSINSTALLDIR%\Team Tools\Static Analysis Tools\Rule Sets`* ます。

次のサンプルカスタムルールセットは、C6001 と C26494 をチェックするようにルールエンジンに指示します。 拡張子がある限り、このファイルを任意の場所に配置 *`.ruleset`* し、引数に完全なパスを指定します。

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description="New rules to apply." ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

::: moniker-end

**`/analyze:stacksize`***番号*\
このオプションと共に使用する *number* パラメーターでは、警告 [C6262](../../code-quality/c6262.md) が生成されるスタックフレームのサイズ (バイト単位) を指定します。 *数値*の前のスペースは省略可能です。 このパラメーターが指定されていない場合、スタックフレームサイズは既定で 16 KB になります。

**`/analyze:WX-`**\
を使用してコンパイルする場合、コード分析の警告はエラーとして扱われません **`/WX`** 。 詳細については、「 [ `/WX` (警告レベル)](compiler-option-warning-level.md)」を参照してください。

## <a name="remarks"></a>注釈

詳細については、「 [c/c + + のコード分析の概要](../../code-quality/code-analysis-for-c-cpp-overview.md) 」および「 [c/c + + のコード分析の警告](../../code-quality/code-analysis-for-c-cpp-warnings.md)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **構成プロパティ**の [  >  **コード分析**の  >  **全般**] プロパティページを選択します。

1. 1つ以上の **コード分析** プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラオプション](compiler-options.md)\
[MSVC コンパイラのコマンドライン構文](compiler-command-line-syntax.md)
