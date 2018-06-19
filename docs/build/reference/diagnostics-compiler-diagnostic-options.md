---
title: -診断 (診断のコンパイラ オプション) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/11/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /diagnostics
- VC.Project.VCCLCompilerTool.DiagnosticsFormat
dev_langs:
- C++
helpviewer_keywords:
- /diagnostics compiler diagnostic options [C++]
- -diagnostics compiler diagnostic options [C++]
- diagnostics compiler diagnostic options [C++]
ms.assetid: db1cc175-6e93-4a2e-9396-c3725d2d8f71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d874e26a922a7f9cce7223b574d525d37733598
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371773"
---
# <a name="diagnostics-compiler-diagnostic-options"></a>/diagnostics (診断のコンパイラ オプション)  
  
使用して、 **/diagnostics**コンパイラ オプションをエラーと警告場所の情報の表示形式を指定します。  
  
## <a name="syntax"></a>構文  
  
```  
/diagnostics:{caret|classic|column}
```  

## <a name="remarks"></a>コメント  
**/Diagnostics**コンパイラ オプションは、エラーおよび警告情報の表示を制御します。  
  
**/Diagnostics:classic**オプションは、の既定値は、問題が見つかった行番号のみを報告します。  
  
**/Diagnostics:column**オプションには、問題が見つかった列も含まれています。 特定の言語コンストラクトまたは問題の原因となっている文字を特定できます。  
  
**/Diagnostics:caret**オプションには、問題が見つかり、コードの行で問題が検出された場所の下のキャレット (^) の配置場所の列が含まれています。  
  
いくつかのケースでは、コンパイラで発生した場所の問題が検出されません。 たとえば、不足しているセミコロン検出できない場合まで、他の予期しないシンボルが発生しました。 列が報告され、カレットの場所、コンパイラでは、何かが間違っています、これは常に、修正を行う必要がありますが検出されましたが配置されます。  
  
**/Diagnostics**オプションは、Visual Studio 2017 以降を使用します。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1. プロジェクトの開く**プロパティ ページ** ダイアログ ボックス。   
  
2. **構成プロパティ**、展開、 **C と C++** フォルダーを選択し、**全般**プロパティ ページ。  
  
3. ドロップダウン コントロールを使用して、**診断形式**フィールド、診断を選択するオプションが表示されます。 選択**OK**または**適用**して変更を保存します。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)