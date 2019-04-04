---
title: /Tc、/Tp、/TC、/TP (ソース ファイル タイプの指定)
ms.date: 1/11/2018
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
ms.openlocfilehash: f7ee51c858c9f90440cf0c2b21799ef7473cf6da
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813865"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc、/Tp、/TC、/TP (ソース ファイル タイプの指定)

**/Tc**オプション C ソース ファイルにそのファイル名引数が .c 拡張機能があるない場合でもを指定します。 **/Tp**オプションが .cpp または .cxx 拡張子があるない場合でも、ファイル名引数が、C++ ソース ファイルを指定します。 オプションと、ファイル名の間にスペースは省略可能です。 各オプションを 1 つのファイルを指定します追加のファイルを指定するには、オプションを繰り返します。

**/TC**と **/TP**はさまざまなグローバル **/Tc**と **/Tp**します。 コンパイラ コマンドラインの C ソース ファイルとしてという名前のすべてのファイルを扱うにするため (**/TC**) または C++ ソース ファイル (**/TP**)、コマンド ライン オプションに関連上の場所に関係なく。 これらのグローバル オプションの 1 つのファイルに上書きできます **/Tc**または **/Tp**します。

## <a name="syntax"></a>構文

> **/Tc** _filename_
>  **/Tp** _filename_
>  **/TC**
>  **/TP**

## <a name="arguments"></a>引数

*ファイル名*<br/>
C または C++ ソース ファイル。

## <a name="remarks"></a>Remarks

既定では、 **CL** .c ファイル拡張子を持つファイルは C ソース ファイルと .cpp または .cxx 拡張子のファイルは、C++ ソース ファイルのことを前提としています。

ときにいずれか、 **TC**または**Tc**オプションを指定すると、仕様、 [/Zc:wchar_t (wchar_t をネイティブ型)](zc-wchar-t-wchar-t-is-native-type.md)オプションは無視されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での設定の C++ コンパイラとビルド プロパティ](../working-with-project-properties.md)を参照してください。

1. 選択、**構成プロパティ** > **C/C++** > **詳細**プロパティ ページ。

1. 変更、**としてコンパイル**プロパティ。 選択**OK**または**適用**変更を適用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>

## <a name="examples"></a>使用例

CL コマンド行では、MAIN.c、TEST.prg と COLLATE.prg がすべての C ソース ファイルを指定します。 CL will not recognize PRINT.prg.

> CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG

CL コマンド行では、TEST1.c、TEST2.cxx、TEST3.huh、および TEST4.o は、C++ ファイルとしてコンパイルし、TEST5.z は C ファイルとしてコンパイルされたことを指定します。

> CL TEST1 します。C TEST2 します。CXX である TEST3 します。ね TEST4 します。O/Tc TEST5 します。Z/TP

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC コンパイラ コマンドラインの構文](compiler-command-line-syntax.md)
