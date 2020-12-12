---
description: /I の詳細情報:/I (追加のインクルードディレクトリ)
title: /I (追加インクルード ディレクトリ)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
ms.openlocfilehash: ad44abec28bbb87f91f449765a9ea2f30f2bffa8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191343"
---
# <a name="i-additional-include-directories"></a>/I (追加インクルード ディレクトリ)

インクルードファイルを検索するディレクトリのリストにディレクトリを追加します。

## <a name="syntax"></a>構文

> **/I**[]*ディレクトリ*

### <a name="arguments"></a>引数

*名簿*<br/>
インクルードファイルを検索するディレクトリの一覧に追加するディレクトリ。

## <a name="remarks"></a>解説

複数のディレクトリを追加するには、このオプションを複数回使用します。 指定されたインクルードファイルが見つかるまで、ディレクトリは検索されません。

このオプションは、([/x (標準インクルードパスを無視する)](x-ignore-standard-include-paths.md)) オプションと共に使用できます。

コンパイラは、次の順序でディレクトリを検索します。

1. 二重引用符形式で [#include ディレクティブ](../../preprocessor/hash-include-directive-c-cpp.md) を使用して指定した場合は、最初にローカルディレクトリが検索されます。 検索は、 **#include** ステートメントを含むファイルと同じディレクトリから開始されます。 このファイルが見つからない場合は、現在開いているインクルードファイルのディレクトリ内で、開いた順に検索します。 ディレクトリの検索は親インクルード ファイルのディレクトリから始まり、上方向へ移動して親の親インクルード ファイルのディレクトリへと続きます。

1. 山かっこ形式の **#include** ディレクティブを使用して指定した場合、またはローカルディレクトリ検索に失敗した場合は、コマンドラインで指定されている順序で、 **/i** オプションを使用して指定されたディレクトリが検索されます。

1. **INCLUDE** 環境変数で指定されたディレクトリ。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[全般]** プロパティ ページを選択します。

1. " **追加のインクルードディレクトリ** " プロパティを変更します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>

## <a name="example"></a>例

次のコマンドは、MAIN によって要求されたインクルードファイルを次の順序で検索します。最初に、二重引用符を使用して指定した場合、ローカルファイルが検索されます。 次に、検索は、-include ディレクトリ、\MY\INCLUDE ディレクトリ、および INCLUDE 環境変数に割り当てられているディレクトリで続行されます。

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
