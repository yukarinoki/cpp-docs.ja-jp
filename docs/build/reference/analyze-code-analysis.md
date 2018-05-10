---
title: 分析 (コード分析) |Microsoft ドキュメント
ms.custom: ''
ms.date: 04/26/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnablePREfast
- /analyze
- VC.Project.VCCLCompilerTool.PREfastAdditionalOptions
- VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins
dev_langs:
- C++
helpviewer_keywords:
- /analyze compiler option [C++]
- -analyze compiler option [C++]
- analyze compiler option [C++]
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4893f30bae3b29538c8bead637cb4d083087a57b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="analyze-code-analysis"></a>/analyze (コード分析)

コード分析とコントロール オプションを有効にします。

## <a name="syntax"></a>構文

```cmd
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only][:ruleset]
```

## <a name="arguments"></a>引数

 /analyze  
 既定のモードで分析をオンにします。 分析の出力に送ら、**出力**他のエラー メッセージのようなウィンドウ。 使用して **/analyze -** 分析を明示的にオフにします。

 /analyze:WX-  
 指定する **/analyze: WX -** を使用してコンパイルするときにコード分析警告することを意味がエラーとして扱われません **/WX**です。 詳細については、「[/w、/W0、/W1、/W2、/W3、/W4, /w1, /w2, /w3、/w4、/Wall、/wd、/we、/wo、/Wv、/WX (警告レベル)](../../build/reference/compiler-option-warning-level.md)」を参照してください。

 /analyze:log `filename`  
 詳細なアナライザーの結果が、`filename` で指定されたファイルに XML として書き込まれます。

 /analyze:quiet  
 アナライザーの出力をオフに、**出力**ウィンドウです。

 /analyze:stacksize `number`  
 `number`パラメーターは、このオプションと共に使用される、サイズのバイトで指定、警告のスタック フレーム[C6262](/visualstudio/code-quality/c6262)が生成されます。 このパラメーターが指定されていない場合は、既定の 16 KB がスタック フレーム サイズとして使用されます。

 /analyze:max_paths `number`  
 このオプションと共に使用される `number` パラメーターでは、分析するコード パスの最大数を指定します。 このパラメーターが指定されていない場合は、既定の 256 が最大数として使用されます。 値を大きくすると、より細かなチェックが実行されますが、分析に時間がかかることがあります。

 /analyze:only  
 通常、コンパイラは、アナライザーを実行した後にコードを生成し、構文チェックをさらに実行します。 **/Analyze: のみ**オプションは、このコード生成パスによってオフ以外の場合はこのため、分析を高速化がコンパイル エラーと、コンパイラのコード生成パスによって検出された警告が出力されません。 プログラムにコード生成のエラーがある場合は、分析結果が信頼できないものになる可能性があるため、このオプションを使用するのは、コードが既にコード生成構文チェックをエラーなしで渡している場合だけにすることをお勧めします。

 /analyze: ruleset `<file_path>.ruleset`  
ことができますを分析するためのルール セットを指定することを自分で作成したカスタム規則セットを含むです。 このスイッチを設定すると、指定した規則を実行する前にセットのメンバー以外を除外するため、ルール エンジンには効率的です。 スイッチが設定されていないと、エンジンは、すべてのルールを確認します。

Visual Studio に付属する ruleset に含まれて **%VSINSTALLDIR%\Team する分析 \rule を設定します。**

次のサンプルのカスタム規則セットでは、ルール エンジン C6001 と C26494 を確認するように指示します。 このファイルを配置するには、任意の場所にある限り、`.ruleset`拡張機能とする引数の完全パスを指定します。

```xml
<?xml version="1.0" encoding="utf-8"?>
<RuleSet Name="New Rule Set" Description=" " ToolsVersion="15.0">
  <Rules AnalyzerId="Microsoft.Analyzers.NativeCodeAnalysis" RuleNamespace="Microsoft.Rules.Native">
    <Rule Id="C6001" Action="Warning" />
    <Rule Id="C26494" Action="Warning" />
  </Rules>
</RuleSet>
```

/analyze: プラグイン  
コード分析の一部が実行されるとは、指定された PREfast プラグインを有効にします。 LocalEspC.dll では、同時実行に関連するコード分析を実装するプラグインの範囲の C261XX 警告チェックです。 たとえば、 [C26100](/visualstudio/code-quality/c26100)、 [C26101](/visualstudio/code-quality/c26101),..., [C26167](/visualstudio/code-quality/c26167)です。

LocalEspC.dll を実行するには、このコンパイラ オプションを使用: **/analyze: プラグイン LocalEspC.dll**

まず CppCoreCheck.dll を実行するには、このコマンドを開発者コマンド プロンプトから実行します。

```cmd
set Esp.Extensions=CppCoreCheck.dll
```

このコンパイラ オプションを使用して: **/analyze: プラグイン EspXEngine.dll**です。

## <a name="remarks"></a>コメント

詳細については、次を参照してください。 [C と C++ の概要のコード分析](/visualstudio/code-quality/code-analysis-for-c-cpp-overview)と[c/c++ の警告のコード分析](/visualstudio/code-quality/code-analysis-for-c-cpp-warnings)です。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 展開して、**構成プロパティ**ノード。

1. 展開して、**コード分析**ノード。

1. **[全般]** プロパティ ページをクリックします。

1. 1 つ以上の変更、**コード分析**プロパティです。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

1. 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A>」を参照してください。

## <a name="see-also"></a>関連項目

- [コンパイラ オプション](../../build/reference/compiler-options.md)
- [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)