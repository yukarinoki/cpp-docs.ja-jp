---
title: コンパイラの警告 (レベル 1) C4717 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4717
dev_langs:
- C++
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fa953d8d41003ff53e721671845c1ddee26da640
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4717"></a>コンパイラの警告 (レベル 1) C4717
'function': すべてのコントロール パスに再帰的で、関数には、ランタイム スタック オーバーフローが発生します  
  
 関数によってすべてのパスには、関数への呼び出しが含まれています。 最初の呼び出さず自体に関数を再帰的に終了する方法はありません、ため、関数は終了しません。  
  
 次の例では、C4717 が生成されます。  
  
```  
// C4717.cpp  
// compile with: /W1 /c  
// C4717 expected  
int func(int x) {  
   if (x > 1)  
      return func(x - 1); // recursive call  
   else {  
      int y = func(0) + 1; // recursive call  
      return y;  
   }  
}  
  
int main(){  
   func(1);  
}  
```