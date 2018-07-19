---
title: -(追加インクルード ディレクトリ) |Microsoft ドキュメント
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
ms.openlocfilehash: 435714d72eeabe74f0cd85509d74dff5d541b019
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373128"
---
# <a name="i-additional-include-directories"></a>/I (追加インクルード ディレクトリ)
インクルード ファイルを検索するディレクトリの一覧に、ディレクトリを追加します。  
  
## <a name="syntax"></a>構文  
  
```  
/I[ ]directory  
```  
  
## <a name="arguments"></a>引数  
 `directory`  
 ディレクトリの一覧に追加するディレクトリは、インクルード ファイルを検索します。  
  
## <a name="remarks"></a>コメント  
 複数のディレクトリを追加するには、このオプションを複数回使用します。 指定したインクルード ファイルが見つかるまでにのみ、ディレクトリが検索されます。  
  
 このオプションを使用するには、標準インクルード パスの無視を ([/X (標準インクルード パスの無視)](../../build/reference/x-ignore-standard-include-paths.md)) オプション。  
  
 コンパイラは、次の順序でディレクトリを検索します。  
  
1.  ソース ファイルを含むディレクトリ。  
  
2.  指定されたディレクトリ、 **/I** CL で出現する順序でのオプションです。  
  
3.  指定したディレクトリ、 **INCLUDE**環境変数。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**全般**プロパティ ページ。  
  
4.  変更、**追加のインクルード ディレクトリ**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>」を参照してください。  
  
## <a name="example"></a>例  
 次のコマンドは次の要求は次の順序でインクルード ファイル: MAIN.c を含む \MY\INCLUDE ディレクトリから、\INCLUDE ディレクトリで、最後にあるディレクトリ内でインクルードに割り当てられているディレクトリに最初に環境変数。  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)