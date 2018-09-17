---
title: -AI (メタデータ ディレクトリの指定) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
dev_langs:
- C++
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 985ff4eb96b904dc9c5b4377b336109b00e06b40
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716593"
---
# <a name="ai-specify-metadata-directories"></a>/AI (メタデータ ディレクトリの指定)

`#using` ディレクティブに渡されたファイル参照を解決するために、コンパイラによって検索されるディレクトリを指定します。

## <a name="syntax"></a>構文

> **/AI**_ディレクトリ_

## <a name="arguments"></a>引数

*ディレクトリ*<br/>
コンパイラが検索するディレクトリまたはパス。

## <a name="remarks"></a>Remarks

1 つだけのディレクトリを渡すことができます、 **/AI**呼び出し。 いずれかを指定 **/AI**コンパイラで検索するパスごとにオプション。 コンパイラ検索パスに C:\Project\Meta と C:\Common\Meta の両方を追加する例では、`#using`ディレクティブを追加`/AI"C:\Project\Meta" /AI"C:\Common\Meta"`コンパイラのコマンドラインを各ディレクトリを追加または、**に関する追加の #using ディレクトリの using**Visual Studio のプロパティです。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

2. 選択、**構成プロパティ** > **C/C++** > **全般**プロパティ ページ。

3. 変更、**に関する追加の #using ディレクトリの using**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)