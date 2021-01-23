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
ms.openlocfilehash: 36da00f9a6d5a55e60efd60a941ac3a9b3bfa4ec
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712792"
---
# <a name="i-additional-include-directories"></a>`/I` (追加のインクルードディレクトリ)

インクルードファイルを検索するディレクトリのリストにディレクトリを追加します。

## <a name="syntax"></a>構文

> **`/I`***ディレクトリ*

### <a name="arguments"></a>引数

*名簿*\
インクルードファイルを検索するディレクトリの一覧に追加するディレクトリ。 とディレクトリの間のスペース `/I` は省略可能です。  スペースを含むディレクトリは、二重引用符で囲む必要があります。 ディレクトリには、絶対パスまたは相対パスを指定できます。

## <a name="remarks"></a>解説

複数のディレクトリを追加するには、このオプションを複数回使用します。 指定されたインクルードファイルが見つかるまで、ディレクトリは検索されません。

このオプションは、([[ `/X` 標準のインクルードパスを無視](x-ignore-standard-include-paths.md)]) オプションと同じコマンドラインで使用できます。

[ `#include` ディレクティブ](../../preprocessor/hash-include-directive-c-cpp.md)は、二重引用符 (またはローカル) 形式で指定できます。たとえば、のようになり `#include "local.h"` ます。 または、山かっこ (または、パス優先) 形式で指定できます。たとえば、のようになり `#include <iostream>` ます。

コンパイラは、次の順序でディレクトリを検索します。

1. **`#include`** 二重引用符を使用してディレクティブを指定した場合は、最初にローカルディレクトリが検索されます。 検索は、ディレクティブを含むファイルと同じディレクトリから開始され **`#include`** ます。 ファイルが見つからない場合は、現在開いているインクルードファイルのディレクトリ内で、開いた順に検索します。 ディレクトリの検索は親インクルード ファイルのディレクトリから始まり、上方向へ移動して親の親インクルード ファイルのディレクトリへと続きます。

1. **`#include`** 山かっこ形式でディレクティブが指定されている場合、またはローカルディレクトリ検索に失敗した場合は、オプションを使用して指定されたディレクトリがコマンドラインで指定されている順序で検索され **`/I`** ます。

1. 環境変数で指定されたディレクトリ **`INCLUDE`** 。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、[Visual Studio での C++ コンパイラとビルド プロパティの設定](../working-with-project-properties.md)に関するページを参照してください。

1. **[構成プロパティ]**  >  **[C/C++]**  >  **[全般]** プロパティ ページを選択します。

1. " **追加のインクルードディレクトリ** " プロパティを変更します。 このプロパティには、一度に複数のディレクトリを指定できます。 ディレクトリはセミコロン () で区切る必要があり **`;`** ます。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>

## <a name="example"></a>例

次のコマンドは、によって要求されたインクルードファイルを *`main.c`* 次の順序で検索します。最初に、二重引用符を使用して指定した場合、ローカルファイルが検索されます。 次に、 *`\include`* ディレクトリ、 *`\my\include`* ディレクトリ、および環境変数に割り当てられているディレクトリ内で、検索が左から右の順序で続行され **`INCLUDE`** ます。

```cmd
CL /I \include /I\my\include main.c
```

## <a name="see-also"></a>関連項目

[MSVC コンパイラ オプション](compiler-options.md)<br/>
[MSVC Compiler Command-Line 構文](compiler-command-line-syntax.md)
