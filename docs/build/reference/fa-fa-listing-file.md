---
title: /FA、/Fa (リスティング ファイル) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AssemblerListingLocation
- VC.Project.VCCLCompilerTool.ConfigureASMListing
- VC.Project.VCCLWCECompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.AssemblerListingLocation
- /fa
- VC.Project.VCCLCompilerTool.AssemblerOutput
- VC.Project.VCCLCompilerTool.UseUnicodeForAssemblerListing
dev_langs:
- C++
helpviewer_keywords:
- FA compiler option [C++]
- /FA compiler option [C++]
- -FA compiler option [C++]
- listing file type
- assembly-only listing
ms.assetid: c7507d0e-c69d-44f9-b8e2-d2c398697402
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03b2f4e746632cc91b652ca76587ddad18afd165
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717965"
---
# <a name="fa-fa-listing-file"></a>/FA、/Fa (リスティング ファイル)

アセンブラー コードを含むリスティング ファイルを作成します。

## <a name="syntax"></a>構文

> **/FA**[**c**\][**s**\]**[u]** **/Fa**_パス名_

## <a name="remarks"></a>Remarks

**/FA**コンパイラ オプションでは、一般に、C または C++ ソース ファイルに対応するコンパイル時に各翻訳単位のアセンブラーのリスティング ファイルが生成されます。 既定では ANSI としてエンコードされるリスティング ファイルにのみアセンブラーが含まれます。 省略可能な**c**、 **s**、および**u**引数 **/FA**マシン コードかどうかのコントロールまたはソース コードは、アセンブラーと出力この一覧を表示すると、一覧を utf-8 としてエンコードするかどうかとします。

既定では、各リスティング ファイルは、ソース ファイルと同じ基本名を取得し、.asm 拡張機能があります。 使用してマシン コードが含まれている場合、 **c**オプション、リスティング ファイル .cod 拡張子が付きます。 リスティング ファイルを使用して作成されるディレクトリの拡張機能と名前を変更することができます、 **/Fa**オプション。

### <a name="fa-arguments"></a>/FA 引数

none<br/>
アセンブラー言語だけでは、一覧に含まれます。

**c**<br/>
任意。 一覧で、マシン語コードが含まれています。

**s**<br/>
任意。 一覧で、ソース コードが含まれています。

**u**<br/>
任意。 Utf-8 形式でリスティング ファイルをエンコードし、バイト順マーカーが含まれています。 既定では、ファイルは ANSI としてエンコードされます。 使用`u`、任意のシステムに正しく表示される、リスティング ファイルを作成するコンパイラへの入力として Unicode を使用しているかどうか、またはソース コード ファイル。

両方**s**と**u**が指定され、ソース コード ファイルの場合は、utf-8 では、その .asm ファイルにコード行が正しく表示されない場合があります以外の Unicode エンコーディングを使用します。

### <a name="fa-argument"></a>/Fa 引数

none<br/>
1 つ*ソース*.asm ファイルがコンパイル時にソース コード ファイルごとに作成されます。

*ファイル名*<br/>
という名前の一覧ファイル*filename*.asm は、現在のディレクトリに配置されます。 1 つのソース コード ファイルをコンパイルするときにのみ有効です。

*filename.extension*<br/>
という名前の一覧ファイル*filename.extension*は、現在のディレクトリに配置されます。 1 つのソース コード ファイルをコンパイルするときにのみ有効です。

*ディレクトリ*__\\__<br/>
1 つ*source_file*.asm ファイルが作成され、指定した配置*ディレクトリ*コンパイル時にソース コード ファイルごとにします。 必要なバック スラッシュに注意してください。 現在のディスク上のパスのみが許可されます。

*ディレクトリ*__\\__*ファイル名*<br/>
という名前の一覧ファイル*filename*.asm の配置で指定した*ディレクトリ*。 1 つのソース コード ファイルをコンパイルするときにのみ有効です。

*ディレクトリ*__\\__*filename.extension*<br/>
という名前の一覧ファイル*filename.extension*に配置されますが、指定した*ディレクトリ*します。 1 つのソース コード ファイルをコンパイルするときにのみ有効です。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

2. 選択、**構成プロパティ** > **C/C++** > **出力ファイル**プロパティ ページ。

3. 変更、**アセンブラー出力**プロパティを設定する、 **/FAc**と **/FAs**アセンブラー、コンピューター、およびソース コードのオプション。 変更、**アセンブラー リストを使用して Unicode**プロパティを設定する、**は/FAu** ANSI または utf-8 の出力オプション。 変更、 **ASM リストの場所**を設定する、 **/Fa**ファイルの名前と場所を一覧表示するためのオプション。

どちらもその設定に注意してください。**アセンブラー出力**と**アセンブラー リストを使用して Unicode**プロパティが発生することができます[コマンドラインの警告 D9025](../../error-messages/tool-errors/command-line-warning-d9025.md)します。 IDE でこれらのオプションを結合する、**追加オプション**フィールドに、**コマンド ライン**プロパティ ページの代わりにします。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 詳細については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerListingLocation%2A>」または「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AssemblerOutput%2A>」を参照してください。 指定する**は/FAu**を参照してください<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>します。

## <a name="example"></a>例

次のコマンドラインは、結合されたソースを生成し、マシン語コード リスティング ファイル hello.cod:

```cmd
CL /FAcs HELLO.CPP
```

## <a name="see-also"></a>関連項目

[出力ファイル (/F) オプション](../../build/reference/output-file-f-options.md)
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[パス名の指定](../../build/reference/specifying-the-pathname.md)