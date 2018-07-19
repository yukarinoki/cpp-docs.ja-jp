---
title: C (プリプロセス時にコメントの保持) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.KeepComments
- /c
- VC.Project.VCCLWCECompilerTool.KeepComments
dev_langs:
- C++
helpviewer_keywords:
- comments, not stripping during preprocessing
- preserve comments during preprocessing
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 944567ca-16bc-4728-befe-d414a7787f26
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 350addc63807a338eb451c14e52340ef67998f18
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371256"
---
# <a name="c-preserve-comments-during-preprocessing"></a>/C (プリプロセス時のコメントの保持)
プリプロセス時にコメントを保持します。  
  
## <a name="syntax"></a>構文  
  
```  
/C  
```  
  
## <a name="remarks"></a>コメント  
 このコンパイラ オプションが必要、 **/E**、 **/P**、または **/EP**オプション。  
  
 次のコード サンプル ソース コードのコメントが表示されます。  
  
```  
// C_compiler_option.cpp  
// compile with: /E /C /c  
int i;   // a variable  
```  
  
 このサンプルでは、次の出力が生成されます。  
  
```  
#line 1 "C_compiler_option.cpp"  
int i;   // a variable  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**プリプロセッサ**プロパティ ページ。  
  
4.  変更、**コメントを残す**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.KeepComments%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/E (プリプロセス stdout へ)](../../build/reference/e-preprocess-to-stdout.md)   
 [/P (ファイルへのプリプロセス)](../../build/reference/p-preprocess-to-a-file.md)   
 [/EP (#line ディレクティブなしで stdout に前処理する)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)