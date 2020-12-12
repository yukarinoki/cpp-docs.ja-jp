---
description: 詳細情報:/C (プリプロセス時のコメントの保持)
title: /C (プリプロセス時のコメントの保持)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- VC.Project.VCCLWCECompilerTool.KeepComments
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
ms.openlocfilehash: 2cf5bf562db78dcb6c570d7313b56ad4a9fc5adb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179357"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (プリプロセス時のコメントの保持)

プリプロセス時にコメントを保持します。

## <a name="syntax"></a>構文

```
/C
```

## <a name="remarks"></a>解説

このコンパイラオプションには、 **/e**、 **/p**、または **/ep** オプションが必要です。

次のコードサンプルでは、ソースコードのコメントが表示されます。

```cpp
// C_compiler_option.cpp
// compile with: /E /C /c
int i;   // a variable
```

このサンプルでは、次の出力が生成されます。

```
#line 1 "C_compiler_option.cpp"
int i;   // a variable
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **プリプロセッサ** ] プロパティページをクリックします。

1. " **コメントの保持** " プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/E (プリプロセス出力の標準出力へのコピー)](e-preprocess-to-stdout.md)<br/>
[/P (ファイルの前処理)](p-preprocess-to-a-file.md)<br/>
[/EP (#line ディレクティブを使用しない stdout へのプリプロセス)](ep-preprocess-to-stdout-without-hash-line-directives.md)
