---
description: :/AI (メタデータディレクトリの指定) の詳細情報
title: /AI (メタデータ ディレクトリの指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
ms.openlocfilehash: e30711b1da2d41204bf56520d56dd5101f3168b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179747"
---
# <a name="ai-specify-metadata-directories"></a>/AI (メタデータ ディレクトリの指定)

`#using` ディレクティブに渡されたファイル参照を解決するために、コンパイラによって検索されるディレクトリを指定します。

## <a name="syntax"></a>構文

> **/Ai**_ディレクトリ_

## <a name="arguments"></a>引数

*名簿*<br/>
コンパイラが検索するディレクトリまたはパス。

## <a name="remarks"></a>解説

**/Ai** 呼び出しに渡すことができるディレクトリは1つだけです。 コンパイラが検索するパスごとに1つの **/ai** オプションを指定します。 たとえば、コンパイラの検索パスに2つのディレクティブを追加するに `#using` `/AI"C:\Project\Meta" /AI"C:\Common\Meta"` は、コンパイラのコマンドラインにを追加するか、Visual Studio の [ **追加の #using ディレクトリ** ] プロパティに各ディレクトリを追加します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[全般]** プロパティ ページを選択します。

1. [ **追加の #using ディレクトリ** のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)
