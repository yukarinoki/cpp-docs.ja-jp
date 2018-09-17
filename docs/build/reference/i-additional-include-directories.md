---
title: -I (追加インクルード ディレクトリ) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
dev_langs:
- C++
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a580488650a1272ec1dffcd1f0ba27c736df92da
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705342"
---
# <a name="i-additional-include-directories"></a>/I (追加インクルード ディレクトリ)

インクルード ファイルを検索するディレクトリの一覧には、ディレクトリを追加します。

## <a name="syntax"></a>構文

```
/I[ ]directory
```

## <a name="arguments"></a>引数

*ディレクトリ*<br/>
ディレクトリの一覧に追加するディレクトリは、インクルード ファイルを検索します。

## <a name="remarks"></a>Remarks

1 つ以上のディレクトリを追加するには、このオプションを複数回使用します。 指定したインクルード ファイルが見つかるまでにのみ、ディレクトリが検索されます。

このオプションを使用するには、標準インクルード パスの無視と ([/X (標準インクルード パスの無視)](../../build/reference/x-ignore-standard-include-paths.md)) オプション。

コンパイラは、次の順序でディレクトリを検索します。

1. ソース ファイルを含むディレクトリ。

1. 指定されたディレクトリ、 **/I** CL で出現する順序でのオプション。

1. 指定されたディレクトリ、 **INCLUDE**環境変数。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. をクリックして、**全般**プロパティ ページ。

1. 変更、**追加のインクルード ディレクトリ**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>

## <a name="example"></a>例

次の順序で MAIN.c によって要求されたインクルード ファイルを探し、次のコマンド: MAIN.c、\INCLUDE ディレクトリから、\MY\INCLUDE ディレクトリ、しを格納していると、最後に、ディレクトリで、インクルードに割り当てられているディレクトリの先頭に環境変数。

```
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C
```

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)