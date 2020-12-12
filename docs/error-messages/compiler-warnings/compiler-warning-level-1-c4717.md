---
description: '詳細情報: コンパイラの警告 (レベル 1) C4717'
title: コンパイラの警告 (レベル 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 7a23469539dd809ea4905701bd1f8064f26a8036
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328133"
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
