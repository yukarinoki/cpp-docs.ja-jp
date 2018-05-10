---
title: -Gw (グローバル データの最適化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Gw
dev_langs:
- C++
helpviewer_keywords:
- /Gw compiler option [C++]
- -Gw compiler option [C++]
ms.assetid: 6f90f4e9-5eb8-4c47-886e-631278a5a4a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 173b9499477ee02cbb1f052d3d85445a9ffb7732
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="gw-optimize-global-data"></a>/Gw (グローバル データの最適化)
グローバル データを最適化のために COMDAT セクションにパッケージ化します。  
  
## <a name="syntax"></a>構文  
  
```  
/Gw[-]  
```  
  
## <a name="remarks"></a>コメント  
 **/Gw**オプションでは、パッケージのグローバル データにコンパイラを個々 の COMDAT セクションでします。 既定では、 **/Gw**がオフでを明示的に有効にする必要があります。 これを明示的に無効にするを使用して **/Gw-** です。 ときに両方 **/Gw**と[/GL](../../build/reference/gl-whole-program-optimization.md)は有効な場合、リンカー全体プログラム最適化を使用して参照されないグローバル データを除外するために、またはマージする複数のオブジェクト ファイル間で COMDAT セクションが比較同一読み取り専用のグローバル データ。 その結果、生成されるバイナリ実行可能ファイルのサイズが大幅に小さくなることがあります。  
  
 コンパイルとは別にリンクすると、使用できます、 [/opt:ref による](../../build/reference/opt-optimizations.md)でのオブジェクト ファイルに参照されないグローバル データがコンパイルされた実行可能ファイルから除外するリンカー オプション、 **/Gw**オプション。  
  
 使用することも、 [/OPT:ICF](../../build/reference/opt-optimizations.md)と[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)で複数のオブジェクト ファイルと同じ読み取り専用でグローバル データがコンパイルされた実行可能ファイルにマージするには、まとめてリンカー オプション、 **/Gw**オプション。  
  
 詳細については、次を参照してください。 [/Gw コンパイラ スイッチの概要](http://blogs.msdn.com/b/vcblog/archive/2013/09/11/introducing-gw-compiler-switch.aspx)Visual c チーム ブログでします。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  選択、 **C/C++** フォルダーです。  
  
3.  選択、**コマンドライン**プロパティ ページ。  
  
4.  変更、**追加オプション**含めるプロパティを **/Gw**を選択し**OK**です。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)