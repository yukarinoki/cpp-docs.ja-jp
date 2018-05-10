---
title: -D (プリプロセッサの定義) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCNMakeTool.PreprocessorDefinitions
- VC.Project.VCCLCompilerTool.PreprocessorDefinitions
- /d
dev_langs:
- C++
helpviewer_keywords:
- preprocessor definition symbols
- constants, defining
- macros, compiling
- /D compiler option [C++]
- -D compiler option [C++]
- D compiler option [C++]
ms.assetid: b53fdda7-8da1-474f-8811-ba7cdcc66dba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b8b386d55804421fb6cb454b4818db52e7cea85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="d-preprocessor-definitions"></a>/D (プリプロセッサの定義)
ソース ファイルのプリプロセッサ シンボルを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
/Dname[= | # [{string | number}] ]  
```  
  
## <a name="remarks"></a>コメント  
 このシンボルを `#if` または `#ifdef` と一緒に使用すると、ソース コードを条件付きでコンパイルできます。 シンボル定義は、コードで再定義されるまで、または `#undef` ディレクティブによってコードで未定義になるまで有効です。  
  
 **/D**と同じ効果を持つ、`#define`点を除いて、ソース コード ファイルの先頭にディレクティブ **/D**コマンドラインの引用符が削除および`#define`は保持されます。  
  
 既定では、シンボルに関連付けられる値は 1 です。 たとえば、 **/D** `name`は等価 **/D**`name`**= 1**です。 例では、この記事では、定義の最後**テスト**を印刷する表示`1`です。  
  
 使用してコンパイルする **/D** `name` **=** により、シンボルに関連付けられた値がないようにします。 シンボルは引き続きコードの条件コンパイルに使用できますが、何も指定されていないものとして評価されます。 使用してコンパイルする場合の例で **/DTEST =** エラーが発生します。 この動作は、値を指定して、または値を指定せずに `#define` を使用する場合と似ています。  
  
 次のコマンドを実行すると、TEST.c で DEBUG シンボルが定義されます。  
  
 **CL/DDEBUG をテストします。C**  
  
 次のコマンドを実行すると、TEST.c からすべての `__far` キーワードが削除されます。  
  
 **CL/D__far テストを = です。C**  
  
 **CL**環境変数は、等号 (=) を含む文字列に設定することはできません。 使用する **/D**と共に、 **CL**環境変数である必要がありますを指定する等号 (=) ではなくシャープ記号。  
  
```  
SET CL=/DTEST#0  
```  
  
 コマンド プロンプトでプリプロセッサ シンボルを定義する場合は、コンパイラ解析規則とシェル解析規則の両方を考慮してください。 たとえば、プログラムでパーセント記号のプリプロセッサ シンボル (%) を定義するには、コマンド プロンプトでパーセント記号 2 文字 (%%) を指定します。パーセント記号を 1 文字だけ指定すると、解析エラーが発生します。  
  
```  
CL /DTEST=%% TEST.C  
```  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、次を参照してください。[のプロジェクト プロパティの操作](../../ide/working-with-project-properties.md)です。  
  
2.  左のペインで選択**構成プロパティ**、 **C/C++**、**プリプロセッサ**です。  
  
3.  右側の列で、右ペインで、**プリプロセッサの定義**プロパティで、ドロップダウン メニューを開き**編集**です。  
  
4.  **プリプロセッサの定義**ダイアログ ボックスで、(1 行につき 1 つ) を追加、変更、または 1 つまたは複数の定義を削除します。 選択**OK**して変更を保存します。  
  
### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PreprocessorDefinitions%2A>」を参照してください。  
  
## <a name="example"></a>例  
  
```  
// cpp_D_compiler_option.cpp  
// compile with: /DTEST  
#include <stdio.h>  
  
int main( )  
{  
    #ifdef TEST  
        printf_s("TEST defined %d\n", TEST);  
    #else  
        printf_s("TEST not defined\n");  
    #endif  
}  
```  
  
```Output  
TEST defined 1  
```  
  
## <a name="see-also"></a>関連項目  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [/U、/u (シンボルを未定義)](../../build/reference/u-u-undefine-symbols.md)   
 [#undef ディレクティブ (C/C++)](../../preprocessor/hash-undef-directive-c-cpp.md)   
 [#define ディレクティブ (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)