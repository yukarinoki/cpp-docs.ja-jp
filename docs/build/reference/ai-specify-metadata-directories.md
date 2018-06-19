---
title: -AI (メタデータ ディレクトリの指定) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.AdditionalUsingDirectories
- VC.Project.VCNMakeTool.AssemblySearchPath
- /AI
- VC.Project.VCCLWCECompilerTool.AdditionalUsingDirectories
dev_langs:
- C++
helpviewer_keywords:
- /AI compiler option [C++]
- AI compiler option [C++]
- -AI compiler option [C++]
ms.assetid: fb9c1846-504c-4a3b-bb39-c8696de32f6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bde5c93c8a211bb0fc66028932a0a7d50415236d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369433"
---
# <a name="ai-specify-metadata-directories"></a>/AI (メタデータ ディレクトリの指定)
`#using` ディレクティブに渡されたファイル参照を解決するために、コンパイラによって検索されるディレクトリを指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/AIdirectory  
```  
  
## <a name="arguments"></a>引数  
 `directory`  
 コンパイラが検索するディレクトリまたはパス。  
  
## <a name="remarks"></a>コメント  
 1 つだけのディレクトリを渡すことができます、 **/AI**呼び出しです。 いずれかを指定 **/AI**コンパイラで検索するパスごとにオプションです。 例については、コンパイラ検索パスに C:\Project\Meta と C:\Common\Meta の両方を追加する`#using`、ディレクティブを追加`/AI"C:\Project\Meta" /AI"C:\Common\Meta"`コンパイラのコマンドラインを各ディレクトリを追加または、**に関する追加の #using ディレクトリの using**Visual Studio でのプロパティです。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  ナビゲーション ウィンドウで、次のように選択します。**構成プロパティ**、 **c/c++**、**全般**です。  
  
3.  変更、**に関する追加の #using ディレクトリを using**プロパティです。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalUsingDirectories%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [#using ディレクティブ](../../preprocessor/hash-using-directive-cpp.md)