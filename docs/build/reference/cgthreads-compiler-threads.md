---
title: -CGTHREADS (コンパイラ スレッド) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- /CGTHREADS linker option
- -CGTHREADS linker option
- CGTHREADS linker option
ms.assetid: 4b52cfdb-3702-470b-9580-fabeb1417488
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5905c29170a7ad636420a9bcdbd282ccfc2e7ec3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="cgthreads-compiler-threads"></a>/CGTHREADS (コンパイラ スレッド)
リンク時のコード生成を指定した場合に最適化とコード生成に使う cl.exe スレッドの数を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
/CGTHREADS:[1-8]  
```  
  
## <a name="arguments"></a>引数  
 number  
 cl.exe が使用できるスレッドの最大数で、1 から 8 の範囲。  
  
## <a name="remarks"></a>コメント  
 **/CGTHREADS**オプションでは、並列スレッド cl.exe 使用の最大数を指定のコンパイルとリンク時の最適化およびコード生成のフェーズのコード生成 ([/LTCG](../../build/reference/ltcg-link-time-code-generation.md)) は指定します。 既定では、cl.exe は 4 つのスレッドを使用してとして **/CGTHREADS:4**が指定されています。 より多くのプロセッサ コアが使用できる場合、より大きい `number` 値はビルド時間を改善できます。  
  
 ビルドでは複数のレベルの並列化を指定できます。 Msbuild.exe スイッチ **/maxcpucount**並列で実行できる MSBuild プロセスの数を指定します。 [/MP (複数のプロセスでビルド)](../../build/reference/mp-build-with-multiple-processes.md)コンパイラ フラグが同時に、ソース ファイルをコンパイルする cl.exe プロセスの数を指定します。 [/Cgthreads](../../build/reference/cgthreads-code-generation-threads.md)コンパイラ オプションは、それぞれの cl.exe プロセスが使用するスレッドの数を指定します。 プロセッサは、プロセッサ コアの数しかスレッドを同時に実行できないため、これらすべてのオプションに、より大きな値を同時に設定するのは効果的ではなく、逆効果になる場合もあります。 並列でプロジェクトをビルドする方法の詳細については、次を参照してください。[並列の複数のプロジェクトをビルドする](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)です。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**構成プロパティ**、**リンカー**フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  変更、**追加のオプション**含めるプロパティを **/CGTHREADS:**`number`ここで、 `number` 1 から 8 の値を選択し**OK**です。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプション](../../build/reference/linker-options.md)   
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)