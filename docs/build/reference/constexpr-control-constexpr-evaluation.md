---
title: constexpr (コントロールの constexpr の評価) |Microsoft ドキュメント
ms.custom: ''
ms.date: 08/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /constexpr
- -constexpr
dev_langs:
- C++
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f83f1d9a505ebc4c05ce4e367bb1e978d6a14b78
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373960"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (コントロールの constexpr の評価)  
  
使用して、 **/constexpr**コンパイラ オプションを制御するパラメーターを`constexpr`コンパイル時に評価します。  
  
## <a name="syntax"></a>構文  
  
> /constexpr:depth*N*  
> /constexpr:backtrace*N*  
> /constexpr:steps*N*  
  
## <a name="arguments"></a>引数  
  
**深さ * * * N*  
再帰の深さを制限`constexpr`関数の呼び出しに*N*レベル。 既定値は 512 です。  
  
**バック * * * N*  
最大表示*N* `constexpr`診断で評価します。 既定値は 10 です。  
  
**手順 * * * N*  
終了`constexpr`後の評価*N*手順を実行します。 既定値は 100,000 です。  
  
## <a name="remarks"></a>コメント  
  
**/Constexpr**コンパイラ オプションを制御のコンパイル時に評価`constexpr`式。 評価手順、再帰レベル、およびバックの深さをコンパイラが上の時間が長くことを防ぐために制御される`constexpr`評価します。 詳細については、`constexpr`言語要素を参照してください[constexpr (C++)](../../cpp/constexpr-cpp.md)です。  

**/Constexpr**オプションは、Visual Studio 2015 以降を使用できます。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1. プロジェクトの開く**プロパティ ページ** ダイアログ ボックス。   
  
2. **構成プロパティ**、展開、 **C/C++** フォルダーを選択し、**コマンド ライン**プロパティ ページ。  
  
3. いずれかを入力 **/constexpr**コンパイラ オプション、**追加オプション**ボックス。 選択**OK**または**適用**して変更を保存します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
  
[コンパイラ オプション](../../build/reference/compiler-options.md)   
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)