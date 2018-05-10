---
title: -GL (プログラム全体の最適化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gl
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
dev_langs:
- C++
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce972b6e7254ad7454f8e8799283588f0fdd5270
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="gl-whole-program-optimization"></a>/GL (プログラム全体の最適化)
プログラム全体の最適化を有効にします。  
  
## <a name="syntax"></a>構文  
  
```  
/GL[-]  
```  
  
## <a name="remarks"></a>コメント  
 プログラム全体の最適化により、コンパイラ、プログラムのすべてのモジュールの情報を含む最適化を実行できます。 最適化が実行全体プログラム最適化を行わず、モジュール (コンパイル単位) ごとです。  
  
 プログラム全体の最適化では、既定ではオフと明示的に有効にする必要があります。 ただし、明示的に無効にすることはも **/GL-** です。  
  
 すべてのモジュールに関する情報は、コンパイラでは次のことができます。  
  
-   関数の境界を越えてレジスタの使用を最適化します。  
  
-   的確に読み込みおよび格納の数を減らしますのグローバル データの変更の追跡を実行します。  
  
-   的確に読み込みおよび格納の数を減らす、可能な項目のセットへのポインターによって変更が逆参照の追跡の操作を行います。  
  
-   インライン関数が別のモジュールで定義されている場合でも、モジュール内の関数。  
  
 生成された .obj ファイル **/GL**としてこのようなリンカー ユーティリティを使用できません[EDITBIN](../../build/reference/editbin-reference.md)と[DUMPBIN](../../build/reference/dumpbin-reference.md)です。  
  
 使用してプログラムをコンパイルする場合 **/GL**と[/c](../../build/reference/c-compile-without-linking.md)、/LTCG リンカー オプションを使用して、出力ファイルを作成する必要があります。  
  
 [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)では使用できません **/GL**  
  
 生成されたファイルの形式 **/GL**現在のバージョンが読み取ることができない以降のバージョンの Visual C。 使って生成された .obj ファイルから成る .lib ファイルを出荷しないで **/GL**ユーザーが現在および将来使用するを期待するすべてのバージョンの Visual C の .lib ファイルのコピーを同梱する意思がない場合。  
  
 生成された .obj ファイル **/GL**プリコンパイル済みヘッダー ファイルは、.lib ファイルは生成される同じコンピューターにリンクする場合を除き、.lib ファイルの作成には使用できません、 **/GL** .obj ファイル。 .Obj ファイルのプリコンパイル済みヘッダー ファイルからの情報は、リンク時に必要になります。  
  
 使用可能な最適化とプログラム全体の最適化の制限事項の詳細については、次を参照してください。 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md)です。  **/GL**もによりプロファイル ガイド付き最適化を使用できない; に/LTCG を参照してください。  プロファイル ガイド付き最適化のプロファイル ガイド付き最適化の順序付け関数をするかどうかをコンパイルするときは、使用してコンパイルする必要があります[/Gy](../../build/reference/gy-enable-function-level-linking.md)またはコンパイラ オプション/Gy のことを意味します。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  参照してください[/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)を指定する方法について **/GL**開発環境でします。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)