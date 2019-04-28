---
title: コンパイラの警告 (レベル 1) C4717
ms.date: 11/04/2016
f1_keywords:
- C4717
helpviewer_keywords:
- C4717
ms.assetid: 5ef3c6c7-8599-4714-a973-0f5b69cdab3c
ms.openlocfilehash: 0cf9aef8f68ca5972fd3d7886cd8061b88d043ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62221142"
---
# <a name="compiler-warning-level-1-c4717"></a>コンパイラの警告 (レベル 1) C4717

'function': すべてのコントロール パスで再帰的で、関数には、ランタイム スタック オーバーフローが発生します

関数のすべてのパスには、関数の呼び出しが含まれています。 最初の呼び出さず自体に関数を再帰的に終了する方法はありません、ため、関数は終了しません。

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