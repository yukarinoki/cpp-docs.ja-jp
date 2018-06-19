---
title: -NODEFAULTLIB (ライブラリの無視) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLinkerTool.OVERWRITEDefaultLibraryNames
- /nodefaultlib
dev_langs:
- C++
helpviewer_keywords:
- default libraries, removing
- -NODEFAULTLIB linker option
- libraries, ignore
- NODEFAULTLIB linker option
- /NODEFAULTLIB linker option
- ignore libraries linker option
ms.assetid: 7270b673-6711-468e-97a7-c2925ac2be6e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 51caac10218d5f4d1787b2256875001ac32dc2b9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375715"
---
# <a name="nodefaultlib-ignore-libraries"></a>/NODEFAULTLIB (ライブラリを無視する)
```  
/NODEFAULTLIB[:library]   
```  
  
## <a name="remarks"></a>コメント  
 それぞれの文字について以下に説明します。  
  
 *ライブラリ*  
 外部参照を解決するときに無視するライブラリです。  
  
## <a name="remarks"></a>コメント  
 /NODEFAULTLIB オプションを使用すると、リンカーは、外部参照を解決するときに、検索するライブラリの一覧から 1 つまたは複数の既定のライブラリを削除します。  
  
 既定のライブラリへの参照が含まれていない .obj ファイルを作成するには、使用[/Zl (既定ライブラリ名の省略)](../../build/reference/zl-omit-default-library-name.md)です。  
  
 既定では、/NODEFAULTLIB は、外部参照を解決するときに、検索するライブラリの一覧からすべての既定のライブラリを削除します。 省略可能な*ライブラリ*パラメーターでは、外部参照を解決するときに、検索するライブラリの一覧から、指定されたライブラリまたはライブラリを削除することができます。 除外する各ライブラリの 1 つの/NODEFAULTLIB オプションを指定します。  
  
 リンカーは、明示的に指定し、次にライブラリが/DEFAULTLIB オプションで指定された既定のライブラリに、次の .obj ファイルの既定のライブラリを最初に検索して、外部定義への参照を解決します。  
  
 /NODEFAULTLIB:*ライブラリ*オーバーライド[/DEFAULTLIB:](../../build/reference/defaultlib-specify-default-library.md)*ライブラリ*とき同じ*ライブラリ*両方の名前を指定します。  
  
 /NODEFAULTLIB を使用する場合など、C ランタイム ライブラリなしプログラムをビルドするしなければならない場合も使用[/ENTRY](../../build/reference/entry-entry-point-symbol.md)をプログラムでエントリ ポイント (関数) を指定します。 詳しくは、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」をご覧ください。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**リンカー**フォルダーです。  
  
3.  クリックして、**入力**プロパティ ページ。  
  
4.  選択、**すべて既定のライブラリの無視**プロパティで無視するライブラリの一覧を指定または、**特定のライブラリの無視**プロパティです。 **コマンドライン**プロパティ ページには、これらのプロパティに加えた変更の効果が表示されます。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreDefaultLibraryNames%2A>」および「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreAllDefaultLibraries%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)