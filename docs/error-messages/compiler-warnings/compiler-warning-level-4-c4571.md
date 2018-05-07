---
title: コンパイラの警告 (レベル 4) C4571 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4571
dev_langs:
- C++
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ecd2223baec2d2ff7e743442d0b44e54c8cb05d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4571"></a>コンパイラの警告 (レベル 4) C4571
Visual C 7.1; から変更情報: catch (...) セマンティクス構造化例外 (SEH) はキャッチされません。  
  
 C4571 はすべて catch (...) のブロックをコンパイルするときに **/EHs**です。  
  
 コンパイルするときに **/EHs**、構造化例外 (null ポインターの例については、0 による除算) 以外の場合は、catch (...) ブロックはのみ catch 明示的にスローされた、C++ の例外を catch (...) のブロックは検出されません。  詳細については、「[例外処理](../../cpp/exception-handling-in-visual-cpp.md)」を参照してください。  
  
 既定では、この警告はオフに設定されています。  この警告でコンパイルするときに確実に有効にする **/EHs** catch (...) ブロックする予定がない構造化例外をキャッチします。  詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
 C4571 を解決するには、次の方法のいずれかで  
  
-   コンパイル時に **/EHa**する場合は、catch (...) ブロックを構造化例外をキャッチします。  
  
-   場合は、catch (...) ブロックを構造化例外をキャッチしないようにする、ブロックの catch (...) を使用する場合でも、C4571 を有効にしないでください。  構造化例外処理キーワードを使用して構造化例外をキャッチすることもできます (**_ _try**、 **_ _except**、および **_ _finally**)。  ただし、コンパイル時に **/EHs**デストラクターは SEH 例外が発生したときではなく、C++ 例外がスローされた場合にのみ呼び出すことです。  
  
-   特定の C++ 例外の catch ブロックと catch (...) のブロックを置き換えるし、構造化例外が C++ 例外処理に処理を必要に応じて、追加 (**_ _try**、 **_ _except**、および **__finally**)。  参照してください[構造化例外処理 (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)詳細についてはします。  
  
 参照してください[/EH (例外処理モデル)](../../build/reference/eh-exception-handling-model.md)詳細についてはします。  
  
## <a name="example"></a>例  
 次の例では、C4571 が生成されます。  
  
```  
// C4571.cpp  
// compile with: /EHs /W4 /c  
#pragma warning(default : 4571)  
int main() {  
   try {  
      int i = 0, j = 1;  
      j /= i;   // this will throw a SE (divide by zero)  
   }  
   catch(...) {}   // C4571 warning  
}  
```