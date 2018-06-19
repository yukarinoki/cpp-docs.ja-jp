---
title: -showincludes (一覧は、ファイルを含める) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs:
- C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6eac7df694994b625e08ded710d43837d857df2d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378341"
---
# <a name="showincludes-list-include-files"></a>/showIncludes (インクルード ファイル一覧)
コンパイラでインクルード ファイルの一覧を出力します。 入れ子になった含めるファイルも表示されている (含まれているファイルからファイルをインクルードする)。  
  
## <a name="syntax"></a>構文  
  
```  
/showIncludes  
```  
  
## <a name="remarks"></a>コメント  
 コンパイル時に、インクルード ファイルを検出したときにメッセージは、出力がたとえばです。  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 入れ子になった含めるなどのファイルは、インデントは、入れ子のレベルごとに 1 つのスペースで示されます。  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 この場合、`2.h`が内から含まれている`1.h`、したがってインデントします。  
  
 **/ShowIncludes**オプションを出力する`stderr`ではなく、`stdout`です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**詳細**プロパティ ページ。  
  
4.  変更、**インクルード ファイルの表示**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)