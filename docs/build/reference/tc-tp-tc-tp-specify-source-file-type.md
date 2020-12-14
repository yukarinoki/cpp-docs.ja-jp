---
description: 詳細情報:/Tc、/Tp、/TC、/TP (ソースファイルの種類を指定)
title: /Tc、/Tp、/TC、/TP (ソース ファイル タイプの指定)
ms.date: 01/11/2018
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.openlocfilehash: 23aed145c8dd9ac36f26bcebe2ea2aab1c39e586
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230030"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc、/Tp、/TC、/TP (ソース ファイル タイプの指定)

**/Tc** オプションは、ファイル名の引数が .c 拡張子を持たない場合でも、c ソースファイルであることを指定します。 **/Tp** オプションは、ファイル名の引数が .cpp または .cxx 拡張子を持たない場合でも、C++ ソースファイルであることを指定します。 オプションとファイル名の間のスペースは省略可能です。 各オプションは、1つのファイルを指定します。追加のファイルを指定するには、オプションを繰り返します。

**/Tc** と **/Tp** は、 **/tc** および **/tp** のグローバルなバリエーションです。 このオプションは、コマンドライン上のオプションに対する場所に関係なく、コマンドラインで指定されたすべてのファイルを C ソースファイル (**/tc**) または C++ ソースファイル (**/tp**) として処理するようコンパイラに指定します。 これらのグローバルオプションは、 **/tc** または **/tp** を使用して1つのファイルで上書きできます。

## <a name="syntax"></a>構文

> **/Tc** _ファイル名_\
> **/Tp** _ファイル名_\
> **/TC**\
> **/TP**

### <a name="arguments"></a>引数

*filename*<br/>
C または C++ のソースファイル。

## <a name="remarks"></a>解説

既定では、 **CL** は拡張子 .c のファイルが c ソースファイルであり、.cpp または .cxx 拡張子のファイルが C++ ソースファイルであると想定しています。

**Tc** または **tc** オプションを指定すると、 [/Zc: Wchar_t (wchar_t はネイティブ型)](zc-wchar-t-wchar-t-is-native-type.md)オプションの指定が無視されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. [**構成プロパティ**] [  >  **C/c + +**]  >  **[詳細設定**] プロパティページを選択します。

1. " **コンパイル** " プロパティを変更します。 **[OK]** または [**適用**] を選択して変更を適用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>

## <a name="examples"></a>例

この CL コマンドラインでは、MAIN、TEST. prg、および COLLATE. prg がすべて C ソースファイルであることを指定します。 CL は印刷を認識しません。

> CL MAIN。C/tctestprg/tcg PRINT。PRG

この CL コマンドラインは、.cxx、TEST3、TEST4 が C++ ファイルとしてコンパイルされ、TEST5 が C ファイルとしてコンパイルされることを指定します。

> CL TEST1。C TEST2。.CXX TEST3。TEST4。O/Tc TEST5。Z/TP

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
