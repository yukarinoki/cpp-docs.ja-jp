---
title: -Zg (関数プロトタイプの生成) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /zg
dev_langs:
- C++
helpviewer_keywords:
- Zg compiler option [C++]
- /Zg compiler option [C++]
- function prototypes, generate function prototypes compiler option
- -Zg compiler option [C++]
- generate function prototypes compiler option
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8288da0981878b17ad0c2091bf2a45569b51740d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380535"
---
# <a name="zg-generate-function-prototypes"></a>/Zg (関数プロトタイプの生成)
削除されました。 ソース ファイルで定義された各関数の関数プロトタイプを作成しますが、ソース ファイルはコンパイルされません。  
  
## <a name="syntax"></a>構文  
  
```  
/Zg  
```  
  
## <a name="remarks"></a>コメント  
 このコンパイラ オプションは使用できなくなりました。 Visual C++ 2015 で削除されました。 このページは、前のバージョンの Visual C++ のユーザーのために残されています。  
  
 関数プロトタイプには、この関数の戻り値の型と引数の型リストが含まれます。 引数の型リストは、関数の仮パラメーターの型から作成されます。 ソース ファイル内に既に存在する関数プロトタイプは無視されます。  
  
 プロトタイプのリストは、標準出力に書き込まれます。 このリストは、関数の実際の引数と仮パラメーターに互換性があることを確認するのに役立ちます。 標準出力をファイルにリダイレクトすることで、リストを保存できます。 その後 **#include** を使って、関数プロトタイプのリストをソース ファイルの一部にすることができます。 これにより、コンパイラは引数の型チェックを実行できます。  
  
 **/Zg** オプションを使っており、構造体型、列挙型、共用体型 (またはそのような型へのポインター) を持つ仮パラメーターがプログラムに含まれる場合、各構造体型、列挙型、共用体型の宣言にはタグ (名前) が必要です。 次の例で、タグ名は `MyStruct`です。  
  
```C  
// Zg_compiler_option.c  
// compile with: /Zg  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```  
  
 **/Zg**オプションが Visual Studio 2005 では使用されなくなり、Visual Studio 2015 では削除されました。 Visual C コンパイラでは、古い、C スタイルのコードのサポートが削除されました。 非推奨のコンパイラ オプションの一覧は、次を参照してください。**廃止予定とコンパイラ オプションの削除**で[コンパイラ オプションの一覧をカテゴリ別](../../build/reference/compiler-options-listed-by-category.md)です。  
  
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