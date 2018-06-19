---
title: /Tc、/Tp、/TC、/TP (ソース ファイルの種類の指定) |Microsoft ドキュメント
ms.date: 1/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
dev_langs:
- C++
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cb612d5c26fd4db51222c480539867d5e506b70
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378107"
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>/Tc、/Tp、/TC、/TP (ソース ファイル タイプの指定)

**/Tc**オプションは、ファイル名引数は C ソース ファイル、.c という拡張子があるない場合でもを指定します。 **/Tp**オプションが、.cpp または .cxx 拡張子を持たない場合でも、ファイル名引数が、C++ ソース ファイルであるを指定します。 オプションとファイル名の間にスペースは省略できます。 各オプションを 1 つのファイルを指定します追加のファイルを指定するには、オプションを繰り返します。

**/TC**と **/TP**のグローバルのバリアントは、 **/Tc**と **/Tp**です。 コンパイラが C ソース ファイルとして名前をコマンドラインですべてのファイルを扱うため (**/TC**) または C++ ソース ファイル (**/TP**)、コマンド ライン オプションに関連して上の場所に関係なく。 これらのグローバル オプションの 1 つのファイルでオーバーライドできます **/Tc**または **/Tp**です。

## <a name="syntax"></a>構文

> **/Tc** _filename_  
> **/Tp** _filename_  
> **/TC**  
> **/TP**  

## <a name="arguments"></a>引数

*ファイル名*  
C または C++ ソース ファイル。

## <a name="remarks"></a>コメント

既定では、 **CL** .c ファイル拡張子を持つファイルは、C ソース ファイルと .cpp または .cxx 拡張子のファイルは、C++ ソース ファイルのことを前提としています。

ときにいずれか、 **TC**または**Tc**オプションを指定するの任意の仕様、 [/Zc:wchar_t (wchar_t をネイティブ型)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md)オプションは無視されます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。

1. 選択、**構成プロパティ** > **C/C++** > **詳細**プロパティ ページ。

1. 変更、**としてコンパイル**プロパティです。 選択**OK**または**適用**して変更を適用します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>」を参照してください。

## <a name="examples"></a>使用例

この CL コマンド ラインでは、MAIN.c、TEST.prg と COLLATE.prg があるすべての C ソース ファイルを指定します。 CL will not recognize PRINT.prg.

> CL メインです。C/TcTEST.PRG/TcCOLLATE.PRG 印刷します。PRG

この CL コマンド ラインでは、TEST1.c、TEST2.cxx、TEST3.huh、および TEST4.o は、C++ ファイルとしてコンパイルし、TEST5.z は C ファイルとしてコンパイルされたことを指定します。

> CL TEST1 です。C TEST2 です。CXX である TEST3 です。良いと思いません TEST4 です。O/Tc TEST5 です。Z/TP

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)  
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)  
