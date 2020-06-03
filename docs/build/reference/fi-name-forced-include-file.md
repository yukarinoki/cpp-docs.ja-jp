---
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
ms.openlocfilehash: 6460f75e2cad81bc1dcc540e3c687de5d0dc0d32
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439802"
---
# <a name="fi-name-forced-include-file"></a>/FI (強制インクルード ファイルの名前の指定)

プリプロセッサによって、指定されたヘッダーファイルが処理されます。

## <a name="syntax"></a>構文

```
/FI[ ]pathname
```

## <a name="remarks"></a>コメント

このオプションは、コマンドラインで指定されたすべてのソースファイルの最初の行、または CL 環境変数、またはコマンドファイルに、二重 `#include` 引用符を使用してファイルを指定するのと同じ効果があります。 複数の **/fi**オプションを使用する場合、ファイルは CL によって処理される順序で含まれます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関する記事を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[詳細設定]** プロパティページをクリックします。

1. **強制インクルードファイル**のプロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- [https://docs.microsoft.com/azure/active-directory/develop/scenario-protected-web-api-overview](<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>) をご覧ください。

## <a name="see-also"></a>参照

[出力ファイル (/F) オプション](output-file-f-options.md)<br/>
[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンド ラインの構文](compiler-command-line-syntax.md)<br/>
[パス名の指定](specifying-the-pathname.md)
