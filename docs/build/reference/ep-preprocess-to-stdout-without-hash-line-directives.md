---
description: :/EP の詳細については、「#line ディレクティブを使用しない stdout へのプリプロセス」を参照してください。
title: /EP (#line ディレクティブを挿入しない stdout へのプリプロセス)
ms.date: 11/04/2016
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
ms.openlocfilehash: cbd36cd6bdafe315a7a6ef01b46857725033bd69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201002"
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP (#line ディレクティブを挿入しない stdout へのプリプロセス)

C と C++ のソースファイルをプリプロセスし、前処理されたファイルを標準出力デバイスにコピーします。

## <a name="syntax"></a>構文

```
/EP
```

## <a name="remarks"></a>解説

このプロセスでは、すべてのプリプロセッサディレクティブが実行され、マクロの展開が実行されて、コメントが削除されます。 プリプロセスされた出力のコメントを保持するには、 **/ep** を使用して、 [/C (プリプロセス時のコメントの保持)](c-preserve-comments-during-preprocessing.md)オプションを使用します。

**/Ep** オプションを指定すると、コンパイルが抑制されます。 コンパイルのために、前処理されたファイルを再送信する必要があります。 **/Ep** は、 **/fa**、 **/fa**、および **/fm** オプションの出力ファイルも抑制します。 詳細については、「 [/fa、/fa (リスティングファイル)](fa-fa-listing-file.md) 」、および「 [/Fm (マップファイル名](fm-name-mapfile.md)の指定)」を参照してください。

処理の後の段階で生成されたエラーは、元のソースファイルではなく、前処理されたファイルの行番号を参照します。 行番号が元のソースファイルを参照するようにするには、代わりに [/e (stdout に前処理する)](e-preprocess-to-stdout.md) を使用します。 **/E** オプションは、 `#line` この目的のためにディレクティブを出力に追加します。

プリプロセスされた出力をディレクティブと共にファイルに送信するに `#line` は、代わりに [/P (ファイルを前処理する)](p-preprocess-to-a-file.md) オプションを使用します。

プリプロセスされた出力を stdout に送信するには、 `#line` ディレクティブで **/P** と **/ep** を一緒に使用します。

**/Ep** オプションでプリコンパイル済みヘッダーを使用することはできません。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **プリプロセッサ** ] プロパティページをクリックします。

1. "前処理された **ファイルの生成** " プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>

## <a name="example"></a>例

次のコマンドラインでは、ファイルをプリコードし、 `ADD.C` コメントを保持し、結果を標準出力デバイスに表示します。

```
CL /EP /C ADD.C
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
