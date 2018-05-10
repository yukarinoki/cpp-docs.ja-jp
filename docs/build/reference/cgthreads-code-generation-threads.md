---
title: -cgthreads (コード生成スレッド) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /cgthreads
dev_langs:
- C++
helpviewer_keywords:
- /cgthreads compiler option (C++)
- -cgthreads compiler option (C++)
- cgthreads compiler option (C++)
- cgthreads
ms.assetid: 64bc768c-6caa-4baf-9dea-7cfa1ffb01c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 32c88fe00958a0fc767d8a316bfe4edab7b4fb0e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="cgthreads-code-generation-threads"></a>/cgthreads (コード生成スレッド)
最適化とコード生成に使用するための cl.exe スレッドの数を設定します。  
  
## <a name="syntax"></a>構文  
  
```  
/cgthreads[1-8]  
```  
  
## <a name="arguments"></a>引数  
 number  
 cl.exe が使用できるスレッドの最大数で、1 から 8 の範囲。  
  
## <a name="remarks"></a>コメント  
 **/Cgthreads**スレッド cl.exe の最大数が並列で使用の最適化とコード生成のフェーズのコンパイルのオプションを指定します。 あることはできませんの間にスペース **/cgthreads**と`number`引数。 既定では、cl.exe は 4 つのスレッドを使用してとして **/cgthreads4**が指定されています。 より多くのプロセッサ コアが使用できる場合、より大きい `number` 値はビルド時間を改善できます。 このオプションと結合されている場合に特に便利[/GL (プログラム全体の最適化)](../../build/reference/gl-whole-program-optimization.md)です。  
  
 ビルドでは複数のレベルの並列化を指定できます。 Msbuild.exe スイッチ **/maxcpucount**並列で実行できる MSBuild プロセスの数を指定します。 [/MP (複数のプロセスでビルド)](../../build/reference/mp-build-with-multiple-processes.md)コンパイラ フラグが同時に、ソース ファイルをコンパイルする cl.exe プロセスの数を指定します。 **/Cgthreads**オプションは、それぞれの cl.exe プロセスが使用するスレッドの数を指定します。 プロセッサは、プロセッサ コアの数しかスレッドを同時に実行できないため、これらすべてのオプションに、より大きな値を同時に設定するのは効果的ではなく、逆効果になる場合もあります。 並列でプロジェクトをビルドする方法の詳細については、次を参照してください。[並列の複数のプロジェクトをビルドする](/visualstudio/msbuild/building-multiple-projects-in-parallel-with-msbuild)です。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**構成プロパティ**、 **C/C++** フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  変更、**追加オプション**含めるプロパティを **/cgthreads**`N`ここで、 `N` 1 から 8 の値を選択し、 **OK**です。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)