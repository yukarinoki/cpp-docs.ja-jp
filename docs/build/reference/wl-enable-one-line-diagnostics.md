---
title: -WL (1 行診断の有効化) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /wl
dev_langs:
- C++
helpviewer_keywords:
- -WL compiler option [C++]
- /WL compiler option [C++]
- WL compiler option [C++]
ms.assetid: 332cadb4-8ea6-45fe-b67d-33ddec1f2c2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 58a6b41e66f7ec37ad02747edb8331049b9baef5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376788"
---
# <a name="wl-enable-one-line-diagnostics"></a>/WL (1 行診断の有効化)
エラーまたは警告メッセージに追加情報を追加します。  
  
## <a name="syntax"></a>構文  
  
```  
/WL  
```  
  
## <a name="remarks"></a>コメント  
 エラーと C++ コンパイラの警告メッセージが続きますが表示されたら、既定では、新しい行に追加の情報です。 コマンドラインからコンパイルするときに、エラーまたは警告メッセージに追加情報の行を追加できます。 ログ ファイルに、ビルド出力をキャプチャして、すべてのエラーと警告を検索するには、そのログを処理する場合、望ましい可能性があります。 セミコロンは、追加の行からエラーまたは警告メッセージを区別します。  
  
 すべてのエラーと警告メッセージは情報の追加の行があります。 次のコードでは、情報の追加行があるエラーを生成します。これにより、使用する場合の効果をテストする **/WL**です。  
  
```  
// compiler_option_WL.cpp  
// compile with: /WL  
#include <queue>  
int main() {  
   std::queue<int> q;  
   q.fromthecontinuum();   // C2039  
}  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  **[C/C++]** フォルダーをクリックします。  
  
3.  **[コマンド ライン]** プロパティ ページをクリックします。  
  
4.  **[追加のオプション]** ボックスにコンパイラ オプションを入力します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)