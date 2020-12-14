---
description: 詳細については、「/FI (強制インクルードファイルの名前の指定)」を参照してください。
title: /FI (強制インクルード ファイルの名前の指定)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
ms.openlocfilehash: 614a06511df1b407adc39bb8ec567a9674ffb3cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200651"
---
# <a name="fi-name-forced-include-file"></a>/FI (強制インクルード ファイルの名前の指定)

プリプロセッサによって、指定されたヘッダーファイルが処理されます。

## <a name="syntax"></a>構文

```
/FI[ ]pathname
```

## <a name="remarks"></a>解説

このオプションは、 `#include` コマンドラインで指定されたすべてのソースファイルの最初の行、または CL 環境変数、またはコマンドファイルに、ディレクティブが二重引用符で囲まれたファイルを指定した場合と同じ効果があります。 複数の **/fi** オプションを使用する場合、ファイルは CL によって処理される順序で含まれます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **詳細設定** ] プロパティページをクリックします。

1. **強制インクルードファイル** のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[パス名の指定](specifying-the-pathname.md)
