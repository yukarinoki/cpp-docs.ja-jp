---
title: /C (プリプロセス時のコメントの保持)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
ms.openlocfilehash: c5854fd1255ab509d8778828de25638dd821d74b
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57821444"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (プリプロセス時のコメントの保持)

プリプロセス時にコメントを保持します。

## <a name="syntax"></a>構文

```
/C
```

## <a name="remarks"></a>Remarks

このコンパイラ オプションが必要です、 **/E**、 **/P**、または **/EP**オプション。

次のコード サンプル ソース コードのコメントが表示されます。

```
// C_compiler_option.cpp
// compile with: /E /C /c
int i;   // a variable
```

このサンプルでは、次の出力が生成されます。

```
#line 1 "C_compiler_option.cpp"
int i;   // a variable
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**プリプロセッサ**プロパティ ページ。

1. 変更、**コメントを残す**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)<br/>
[/E (stdout に前処理する)](e-preprocess-to-stdout.md)<br/>
[/P (ファイルの前処理)](p-preprocess-to-a-file.md)<br/>
[/EP (#line ディレクティブなしで stdout に前処理する)](ep-preprocess-to-stdout-without-hash-line-directives.md)
