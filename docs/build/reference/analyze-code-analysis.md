---
title: /analyze (コード分析)
ms.date: 10/01/2019
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
ms.openlocfilehash: d647045d76dc32544f8146424b220547890b0943
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816330"
---
# <a name="analyze-code-analysis"></a>/analyze (コード分析)

コード分析とコントロール オプションを有効にします。

## <a name="syntax"></a>構文

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>引数

/analyze は、既定のモードで分析をオンにします。 分析出力は、他のエラーメッセージと同様に**出力**ウィンドウに移動します。 分析を明示的にオフにするには **、/analyze e-** を使用します。

/analyze: WX- **/analyze: wx**を指定します。 **/wx**を使用してコンパイルするときに、コード分析の警告がエラーとして扱われないことを意味します。 詳細については、「[/w、/W0、/W1、/W2、/W3、/W4, /w1, /w2, /w3、/w4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)](compiler-option-warning-level.md)」を参照してください。

/analyze: log `filename` 詳細なアナライザーの結果は、`filename` によって指定されたファイルに XML として書き込まれます。

/analyze: quiet では、アナライザーの出力が**出力**ウィンドウに表示されません。

/analyze: stacksize `number` `number` パラメーターこのオプションと共に使用されるパラメーターは、警告[C6262](/visualstudio/code-quality/c6262)が生成されるスタックフレームのサイズ (バイト単位) を指定します。 0 @no__t 前のスペースは省略可能です。 このパラメーターが指定されていない場合は、既定の 16 KB がスタック フレーム サイズとして使用されます。

/analyze: max_paths `number` このオプションで使用される `number` パラメーターには、分析するコードパスの最大数を指定します。 このパラメーターが指定されていない場合は、既定の 256 が最大数として使用されます。 値を大きくすると、より細かなチェックが実行されますが、分析に時間がかかることがあります。

/analyze: 通常は、コンパイラによってコードが生成され、アナライザーの実行後により多くの構文チェックが行われます。 **/Analyze: only**オプションは、このコード生成パスをオフにします。これにより、分析が高速になりますが、コンパイラのコード生成パスによって検出されたコンパイルエラーと警告は出力されません。 プログラムにコード生成のエラーがある場合は、分析結果が信頼できないものになる可能性があるため、このオプションを使用するのは、コードが既にコード生成構文チェックをエラーなしで渡している場合だけにすることをお勧めします。

/analyze: ルールセット `<file_path>.ruleset` を使用すると、自分で作成できるカスタム規則セットを含む、分析する規則セットを指定できます。 このスイッチが設定されている場合、ルールエンジンは、実行前に指定された規則セットの非メンバーを除外するため、より効率的です。 スイッチが設定されていない場合、エンジンはすべての規則を確認します。

Visual Studio に付属しているルールセットは、%VSINSTALLDIR%\Team ツールの **静的な分析ツール \ ルールセットの設定**に含まれています。

次のサンプルカスタムルールセットは、C6001 と C26494 をチェックするようにルールエンジンに指示します。 このファイルは、@no__t 0 の拡張子が付いている限り、任意の場所に配置できます。引数に完全なパスを指定します。

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/analyze: プラグインは、コード分析の実行の一部として、指定された PREfast プラグインを有効にします。
LocalC261XX は、同時実行に関連するコード分析チェックを実装するプラグインです。 たとえば、 [C26100](/visualstudio/code-quality/c26100)、 [C26101](/visualstudio/code-quality/c26101)、 [C26167](/visualstudio/code-quality/c26167)のようになります。

Local、c .dll を実行するには、次のコンパイラオプションを使用します。 **/analyze: Plugin Localて c .dll**

CppCoreCheck を実行するには、まず開発者コマンドプロンプトから次のコマンドを実行します。

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

その後、次のコンパイラオプションを使用します。 **/analyze: プラグイン**では、dll を使用します。

## <a name="remarks"></a>コメント

詳細については、「 [c/C++ ](/visualstudio/code-quality/code-analysis-for-c-cpp-overview) c + + のコード分析」と「 [c/C++警告のコード分析](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. **[コード分析]** ノードを展開します。

1. **[全般]** プロパティ ページをクリックします。

1. 1つ以上の**コード分析**プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>

## <a name="see-also"></a>関連項目

- [MSVC コンパイラ オプション](compiler-options.md)
- [MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)
