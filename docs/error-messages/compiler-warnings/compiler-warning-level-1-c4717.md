---
title: コンパイラの警告 (レベル 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 40897e54601793431671bc14f855db43e905c656
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175289"
---
# <a name="compiler-warning-level-1-c4717"></a>コンパイラの警告 (レベル 1) C4717

' function ': すべてのコントロールパスで再帰的に行われます。関数は、ランタイムスタックオーバーフローを発生させます

関数を使用するすべてのパスには、関数の呼び出しが含まれます。 最初にそれ自体を再帰的に呼び出すことなく関数を終了する方法がないため、関数は終了しません。

次の例では、C4717 が生成されます。

```cpp
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
