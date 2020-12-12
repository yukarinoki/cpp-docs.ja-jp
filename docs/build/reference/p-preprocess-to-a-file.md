---
description: 詳細については、次を参照してください:/P (ファイルに前処理する)
title: /P (プリプロセス出力のファイルへの書き込み)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
ms.openlocfilehash: 20bca03694c866baa0575445271fc4f587268096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226195"
---
# <a name="p-preprocess-to-a-file"></a>/P (プリプロセス出力のファイルへの書き込み)

C と C++ のソースファイルをプリプロセスし、前処理された出力をファイルに書き込みます。

## <a name="syntax"></a>構文

```
/P
```

## <a name="remarks"></a>解説

ファイルの基本名は、ソースファイルと拡張子が i です。 このプロセスでは、すべてのプリプロセッサディレクティブが実行され、マクロの展開が実行されて、コメントが削除されます。 前処理された出力のコメントを保持するには、 **/p** を使用して、 [/C (プリプロセス時のコメントの保持)](c-preserve-comments-during-preprocessing.md)オプションを使用します。

**/P** `#line` は、含まれている各ファイルの先頭と末尾に、条件付きコンパイルのプリプロセッサディレクティブによって削除された行の前後にディレクティブを追加します。 これらのディレクティブは、前処理されたファイルの行の番号を付けます。 その結果、処理の後の段階で生成されたエラーは、前処理されたファイル内の行ではなく、元のソースファイルの行番号を参照します。 ディレクティブを生成しないようにするには `#line` 、 [/ep (#line ディレクティブを使用せずに stdout に](ep-preprocess-to-stdout-without-hash-line-directives.md) 前処理) と **/p** を使用します。

**/P** オプションを指定すると、コンパイルが抑制されます。 [/Fo (オブジェクトファイル名)](fo-object-file-name.md)を使用した場合でも、.obj ファイルは生成されません。 コンパイルのために、前処理されたファイルを再送信する必要があります。 **/P** では、 **/fa**、 **/fa**、および **/fm** オプションの出力ファイルも抑制されます。 詳細については、「 [/fa、/fa (リスティングファイル)](fa-fa-listing-file.md) 」、および「 [/Fm (マップファイル名](fm-name-mapfile.md)の指定)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. [ **プリプロセッサ** ] プロパティページをクリックします。

1. "前処理された **ファイルの生成** " プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>

## <a name="example"></a>例

次のコマンドラインでは、のプリコードを実行し、 `ADD.C` コメントを保持 `#line` し、ディレクティブを追加して、結果をファイルに書き込み `ADD.I` ます。

```
CL /P /C ADD.C
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)<br/>
[/Fi (出力ファイル名のプリプロセス)](fi-preprocess-output-file-name.md)
