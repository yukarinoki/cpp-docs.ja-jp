---
title: /FA、/Fa (リスティング ファイル)
description: Microsoft C++/FA と/Fa (リスティングファイル) コンパイラオプションのリファレンスガイドです。
ms.date: 11/21/2020
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.openlocfilehash: 7e8e39fea55bb69eaa0ae914eeabcafef4ac7849
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440241"
---
# <a name="fa-fa-listing-file"></a>`/FA`、 `/Fa` (リスティングファイル)

アセンブラコードを含むリスティングファイルを作成します。

## <a name="syntax"></a>構文

> **`/FA`**[**`c`**\][**`s`**\][**`u`**]\
> **`/Fa`**_パス名_

## <a name="remarks"></a>注釈

**`/FA`** コンパイラオプションは、コンパイル時に各翻訳単位のアセンブラリスティングファイルを生成します。このファイルは、通常、C または C++ のソースファイルに対応しています。 既定では、アセンブラーのみが、ANSI としてエンコードされたリスティングファイルに含まれています。 **`c`** **`s`** **`u`** **`/FA`** コンピューターコードまたはソースコードをアセンブラリストと共に出力するかどうか、およびリストを utf-8 としてエンコードするかどうかを制御する省略可能な、、およびの各引数。

既定では、各リスティングファイルはソースファイルと同じベース名を取得し、拡張子が付き *`.asm`* ます。 オプションを使用してマシンコードを含めると **`c`** 、リスティングファイルに拡張子が付き *`.cod`* ます。 オプションを使用すると、リスティングファイルの名前と拡張子、およびリストファイルが作成されたディレクトリを変更でき **`/Fa`** ます。

### <a name="fa-arguments"></a>`/FA` 引数

存在
アセンブラ言語のみが一覧に含まれています。

**`c`**\
任意。 一覧にコンピューターコードを含めます。

**`s`**\
任意。 一覧にソースコードを含めます。

**`u`**\
任意。 リスティングファイルを UTF-8 形式でエンコードし、バイト順マーカーを含めます。 既定では、ファイルは ANSI としてエンコードされます。 **`u`** を使用すると、任意のシステムに正しく表示されるリスティングファイルを作成できます。また、コンパイラへの入力として Unicode ソースコードファイルを使用している場合は、を使用します。

との **`s`** 両方 **`u`** が指定され、ソースコードファイルで utf-8 以外の Unicode エンコーディングが使用されている場合は、ファイル内のコード行 *`.asm`* が正しく表示されない可能性があります。

### <a name="fa-argument"></a>`/Fa` 引数

存在
コンパイル時にソースコードファイルごとに1つの *ソース .asm* ファイルが作成されます。

*/db*\
コンパイラは、 *filename* という名前のリスティングファイルを現在のディレクトリに配置します。 この引数の形式は、1つのソースコードファイルをコンパイルする場合にのみ有効です。

*ファイル名拡張子*\
コンパイラは、現在のディレクトリに *filename. 拡張子* という名前のリスティングファイルを配置します。 この引数の形式は、1つのソースコードファイルをコンパイルする場合にのみ有効です。

*名簿*__\\__\
コンパイラは、コンパイル時にソースコードファイルごとに1つの *source_file .asm* ファイルを作成します。 指定した *ディレクトリ* に配置されます。 末尾の円記号が必要です。 現在のディスク上のパスのみが許可されます。

*ディレクトリ* __\\__*ファイル名*\
*Filename* という名前のリスティングファイルが、指定された *ディレクトリ* に配置されます。 この引数の形式は、1つのソースコードファイルをコンパイルする場合にのみ有効です。

*ディレクトリ* __\\__*ファイル名拡張子*\
指定された *ディレクトリ* には、*ファイル名拡張子* が付いたリスティングファイルが配置されます。 この引数の形式は、1つのソースコードファイルをコンパイルする場合にのみ有効です。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**  >  **出力ファイル**] プロパティページを選択します。

1. アセンブラー **出力** プロパティを変更して、アセンブラー、コンピューター、およびソースコードの **/FAc** オプションと **/fa** オプションを設定します。 [ **アセンブラーリスティングに Unicode を使用** する] プロパティを変更して、 **`/FAu`** ANSI または utf-8 出力のオプションを設定します。 **ASM リストの場所** を変更して、 **`/Fa`** ファイル名と場所を一覧表示するオプションを設定します。

**アセンブラ出力** の両方を設定し、**アセンブラーリスティングプロパティに Unicode を使用** すると、[コマンドラインの警告 D9025](../../error-messages/tool-errors/command-line-warning-d9025.md)が発生する可能性があります。 IDE でこれらのオプションを組み合わせるには、代わりに [**コマンドライン**] プロパティページの [**追加のオプション**] フィールドを使用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 詳細については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A>」または「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>」を参照してください。 **/FAu** を指定するには、「」を参照してください <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> 。

## <a name="example"></a>例

次のコマンドラインでは、と呼ばれる、結合されたソースとコンピューターコードの一覧が生成され *`HELLO.cod`* ます。

```cmd
CL /FAcs HELLO.CPP
```

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](output-file-f-options.md)\
[MSVC コンパイラオプション](compiler-options.md)\
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)\
[パス名の指定](specifying-the-pathname.md)
