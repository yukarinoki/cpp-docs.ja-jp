---
title: /analyze (コード分析)
ms.date: 04/26/2018
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
ms.openlocfilehash: 63cfd2bd206a361301c75110a684e1d2c642a1f2
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/15/2019
ms.locfileid: "57819507"
---
# <a name="analyze-code-analysis"></a>/analyze (コード分析)

コード分析とコントロール オプションを有効にします。

## <a name="syntax"></a>構文

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>引数

/analyze に既定のモードで分析します。 分析の出力に送ら、**出力**他のエラー メッセージのようなウィンドウ。 使用 **/analyze -** 分析を明示的にオフにします。

/analyze: WX 指定 **/analyze: WX -** を使用してコンパイルするときにコード分析の警告がエラーとして扱われなく **/WX**します。 詳細については、「[/w、/W0、/W1、/W2、/W3、/W4, /w1, /w2, /w3、/w4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)](compiler-option-warning-level.md)」を参照してください。

/analyze: ログ`filename`詳細なアナライザーの結果で指定されているファイルに XML として書き込まれます`filename`します。

/analyze: アナライザーの出力をオフになりますを quiet、**出力**ウィンドウ。

/analyze:/analyze:stacksize `number` 、`number`このオプションで使用されるパラメーターは、警告のスタック フレームのバイト単位でサイズを指定[C6262](/visualstudio/code-quality/c6262)が生成されます。 このパラメーターが指定されていない場合は、既定の 16 KB がスタック フレーム サイズとして使用されます。

/analyze:/analyze:max_paths `number` 、`number`このオプションで使用されるパラメーターを分析するコード パスの最大数を指定します。 このパラメーターが指定されていない場合は、既定の 256 が最大数として使用されます。 値を大きくすると、より細かなチェックが実行されますが、分析に時間がかかることがあります。

/analyze: 通常、コンパイラはコードを生成し、構文チェック、アナライザーを実行した後をさらには専用です。 **/Analyze: のみ**オプションは、このコード生成パスによってオフします。 分析を高速化により、これがコンパイル エラーとコンパイラのコード生成パスによって検出された警告が出力されません。 プログラムにコード生成のエラーがある場合は、分析結果が信頼できないものになる可能性があるため、このオプションを使用するのは、コードが既にコード生成構文チェックをエラーなしで渡している場合だけにすることをお勧めします。

/analyze: ruleset`<file_path>.ruleset`などのカスタム規則セットを自分で作成できることを分析するルールのセットを指定することができます。 このスイッチが設定されている場合、指定した規則を実行する前にセットのメンバー以外を除外するため、ルール エンジンが効率的です。 スイッチが設定されていない場合、エンジンはすべてのルールを確認します。

Visual Studio に付属する ruleset にあるは **%VSINSTALLDIR%\Team \static 分析 Tools\Rule セット。**

次のサンプルのカスタム規則セットでは、ルール エンジン C6001 と C26494 を確認するように指示します。 このファイルを配置するには、任意の場所にある限り、`.ruleset`と拡張機能は、引数の完全なパスを指定します。

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/analyze: プラグインがコード分析の一部を実行すると、指定された PREfast プラグインをできます。
LocalEspC.dll は、範囲の C261XX 警告で同時実行関連のコード分析を実装するプラグインを確認します。 たとえば、 [C26100](/visualstudio/code-quality/c26100)、 [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167)します。

LocalEspC.dll を実行するには、このコンパイラ オプションを使用: **/analyze: プラグイン LocalEspC.dll**

CppCoreCheck.dll を実行するには、最初の開発者コマンド プロンプトからこのコマンドを実行します。

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

このコンパイラ オプションを使用して: **/analyze: プラグイン EspXEngine.dll**します。

## <a name="remarks"></a>Remarks

詳細については、[Code Analysis for C と C++ の概要](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)と[c/c++ の警告のコード分析](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings)を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. **[構成プロパティ]** ノードを展開します。

1. 展開、**コード分析**ノード。

1. **[全般]** プロパティ ページをクリックします。

1. 1 つ以上の変更、**コード分析**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

1. 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>

## <a name="see-also"></a>関連項目

- [MSVC コンパイラ オプション](compiler-options.md)
- [MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)
