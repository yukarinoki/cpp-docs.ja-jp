---
title: U-u (シンボルを未定義) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
dev_langs:
- C++
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 897ca229ec7312812b6f2bd2991bf519e98c836c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32378328"
---
# <a name="u-u-undefine-symbols"></a>/U、/u (定義済みマクロ シンボルの未定義化)
**/U**コンパイラ オプションの指定したプリプロセッサ シンボル定義を解除します。 **/U**コンパイラ オプションのコンパイラを定義する Microsoft 固有のシンボル定義を解除します。  
  
## <a name="syntax"></a>構文  
  
```  
/U[ ]symbol  
/u  
```  
  
## <a name="arguments"></a>引数  
 `symbol`  
 未定義にするプリプロセッサ シンボル。  
  
## <a name="remarks"></a>コメント  
 どちらも、 **/U**または **/u**オプションを使用して作成されたシンボルを未定義ことができます、 **#define**ディレクティブです。  
  
 **/U**オプションを使用して以前に定義されたシンボルを未定義ことができます、 **/D**オプション。  
  
 既定では、コンパイラは、次の Microsoft 固有のシンボルを定義します。  
  
|シンボル|関数|  
|------------|--------------|  
|_CHAR_UNSIGNED|既定の char 型が署名されていません。 定義されているときに、 [/J](../../build/reference/j-default-char-type-is-unsigned.md)オプションを指定します。|  
|_CPPRTTI|コンパイルされたコードに対して定義されている、 [/GR](../../build/reference/gr-enable-run-time-type-information.md)オプション。|  
|_CPPUNWIND|コンパイルされたコードに対して定義されている、 [/EHsc](../../build/reference/eh-exception-handling-model.md)オプション。|  
|_DLL|定義されているときに、 [/MD](../../build/reference/md-mt-ld-use-run-time-library.md)オプションを指定します。|  
|_M_IX86|既定では、x86 を 600 に定義されているターゲットです。|  
|_MSC_VER|詳細については、「 [Predefined Macros](../../preprocessor/predefined-macros.md)」を参照してください。|  
|_WIN32|WIN32 アプリケーションで定義されています。 これは、常に定義されます。|  
|_MT|定義されているときに、 [/MD、/MT または](../../build/reference/md-mt-ld-use-run-time-library.md)オプションを指定します。|  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  クリックして、**詳細**プロパティ ページ。  
  
4.  変更、**指定したプリプロセッサ定義**または**定義済みプリプロセッサ定義**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   詳細については、「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A>」または「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/J (既定の char 型の unsigned)](../../build/reference/j-default-char-type-is-unsigned.md)   
 [/GR (ランタイム型情報の有効化)](../../build/reference/gr-enable-run-time-type-information.md)   
 [/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)   
 [/MD、/MT、/LD (ランタイム ライブラリの使用)](../../build/reference/md-mt-ld-use-run-time-library.md)