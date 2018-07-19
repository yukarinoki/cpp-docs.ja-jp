---
title: 関数インライン展開の問題 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 670136a61d5991655a5d99e8257c6bcc907f2dfb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300229"
---
# <a name="function-inlining-problems"></a>関数インライン展開の問題
関数のインライン展開を使用している必要があります。  
  
-   追加するヘッダー ファイルで実装されたインライン関数があります。  
  
-   インライン展開ヘッダー ファイルでオンにします。  
  
```  
// LNK2019_function_inline.cpp  
// compile with: /c   
// post-build command: lib LNK2019_function_inline.obj  
#include <stdio.h>  
struct _load_config_used {  
   void Test();  
   void Test2() { printf("in Test2\n"); }  
};  
  
void _load_config_used::Test() { printf("in Test\n"); }  
```  
  
 この場合、次のようになります。  
  
```  
// LNK2019_function_inline_2.cpp  
// compile with: LNK2019_function_inline.lib  
struct _load_config_used {  
   void Test();  
   void Test2();  
};  
  
int main() {  
   _load_config_used x;  
   x.Test();  
   x.Test2();   // LNK2019  
}  
```  
  
 使用している場合、`#pragma inline_depth`コンパイラ ディレクティブを確認する値が 2 以上設定されています。 ゼロの値がオフにインライン展開されます。 使用しているかどうかを確認も、 **/Ob1**または **/Ob2**コンパイラ オプション。  
  
 異なるモジュールでのインライン バージョンおよびインライン以外のコンパイル オプションが混在と、問題が発生することができる場合があります。 C++ ライブラリがオンになっている関数のインライン展開で作成されたかどうか ([/Ob1](../../build/reference/ob-inline-function-expansion.md)または[/Ob2](../../build/reference/ob-inline-function-expansion.md)) が、関数を記述する、対応するヘッダー ファイル (オプションではありません) を無効になっていると、エラー LNK2001 が発生します。 関数は、コードにインライン展開されてから取得、ヘッダー ファイルが、参照を解決するのにはアドレスがありませんので、ライブラリ ファイルではありません。  
  
 同様に、関数のインライン展開を使用するプロジェクトをまだ関数を定義します .cpp ファイルではなく、ヘッダー ファイルは lnk2019 です。 ヘッダー ファイルが含まれるすべての場所、適切と見なされますが、関数はのみインライン関数では、.cpp ファイルは、コンパイラを通過するときそのため、リンカーでは、.cpp ファイルの他のモジュールで使用する場合、関数が表示されます。  
  
```  
// LNK2019_FIP.h  
struct testclass {  
   void PublicStatMemFunc1(void);  
};  
```  
  
 それから  
  
```  
// LNK2019_FIP.cpp  
// compile with: /c  
#include "LNK2019_FIP.h"  
inline void testclass::PublicStatMemFunc1(void) {}  
```  
  
 それから  
  
```  
// LNK2019_FIP_2.cpp  
// compile with: LNK2019_FIP.cpp  
// LNK2019 expected  
#include "LNK2019_FIP.h"  
int main() {  
   testclass testclsObject;  
  
   // module cannot see the implementation of PublicStatMemFunc1  
   testclsObject.PublicStatMemFunc1();  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [リンカー ツール エラー LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)