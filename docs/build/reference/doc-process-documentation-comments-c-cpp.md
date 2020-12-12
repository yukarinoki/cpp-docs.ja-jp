---
description: 詳細情報:/doc (ドキュメントコメントの処理) (C/c + +)
title: /doc (ドキュメント コメントの処理) (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
ms.openlocfilehash: ed811edff544c4b5b28baa67ed216fa09ea51092
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192877"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (ドキュメント コメントの処理) (C/C++)

コンパイラがソースコードファイル内のドキュメントコメントを処理し、ドキュメントコメントのあるソースコードファイルごとに .xdc ファイルを作成します。

## <a name="syntax"></a>構文

> **/doc**[*名前*]

## <a name="arguments"></a>引数

*name*<br/>
コンパイラが作成する .xdc ファイルの名前。 1つの .cpp ファイルがコンパイルで渡された場合にのみ有効です。

## <a name="remarks"></a>解説

.Xdc ファイルは、xdcmake.exe で .xml ファイルに処理されます。 詳細については、「 [XDCMake Reference](xdcmake-reference.md)」を参照してください。

ドキュメントのコメントをソースコードファイルに追加できます。 詳細については、「 [ドキュメント コメント用の推奨タグ](recommended-tags-for-documentation-comments-visual-cpp.md)」を参照してください。

生成された .xml ファイルを IntelliSense で使用するには、.xml ファイルのファイル名をサポートするアセンブリと同じにして、.xml ファイルをアセンブリと同じディレクトリに配置します。 アセンブリが Visual Studio プロジェクトで参照されている場合は、.xml ファイルも検出されます。 詳細については、「 [IntelliSense の使用](/visualstudio/ide/using-intellisense) 」および「 [XML コードコメントの指定](/visualstudio/ide/supplying-xml-code-comments)」を参照してください。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **出力ファイル**] プロパティページを選択します。

1. " **XML ドキュメントファイルの生成** " プロパティを変更します。

### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
