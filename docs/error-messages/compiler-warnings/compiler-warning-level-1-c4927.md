---
title: コンパイラの警告 (レベル 1) C4927
ms.date: 11/04/2016
f1_keywords:
- C4927
helpviewer_keywords:
- C4927
ms.assetid: 7009e740-a2ef-4130-96ba-482e092f717a
ms.openlocfilehash: 59a39e4e695fdd161135cd70a74e1f3f6518e361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50542211"
---
# <a name="compiler-warning-level-1-c4927"></a>コンパイラの警告 (レベル 1) C4927

変換が正しくありません。1 つ以上のユーザー定義の変換が暗黙的に適用されています。

1 つ以上のユーザー定義の変換は、単一の値に暗黙的に適用、コンパイラは明示的な変換が見つかりませんでしたが、利用、変換が見つかりました。

次の例では、C4927 が生成されます。

```
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