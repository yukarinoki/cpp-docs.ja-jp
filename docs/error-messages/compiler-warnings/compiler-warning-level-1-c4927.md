---
description: '詳細情報: コンパイラの警告 (レベル 1) C4927'
title: コンパイラの警告 (レベル 1) C4927
ms.date: 11/04/2016
f1_keywords:
- C4927
helpviewer_keywords:
- C4927
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
ms.openlocfilehash: ddd131a5b87004fba56e80adbe5d9bea263f376a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301868"
---
# <a name="compiler-warning-level-1-c4927"></a>コンパイラの警告 (レベル 1) C4927

無効な変換です。複数のユーザー定義の変換が暗黙的に適用されています

複数のユーザー定義の変換が1つの値に暗黙的に適用されています。コンパイラは明示的な変換を検出しませんでしたが、使用されている変換が見つかりました。

次の例では、C4927 が生成されます。

```cpp
// C4927.cpp
// compile with: /W1
struct B
{
   operator int ()
   {
      return 0;
   }
};

struct A
{
   A(int i)
   {
   }

   /*
   // uncomment this constructor to resolve
   A(B b)
   {
   }
   */
};

A f1( B& b)
{
   return A(b);
}

B& f2( B& b)
{
   return b;
}

A f()
{
   B b;
   return A(b);   // ok
   return f1(b);  // ok
   return b;      // C4927
   return B(b);   // C4927
   return f2(b);  // C4927
}

int main()
{
   B b;
   A a = b;
   A a2(b);
}
```
