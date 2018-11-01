---
title: コンパイラの警告 (レベル 1) C4358
ms.date: 11/04/2016
f1_keywords:
- C4358
helpviewer_keywords:
- C4358
ms.assetid: a9848f84-14b3-405e-81bf-ee3e91a51511
ms.openlocfilehash: aebac17a343efedf678b55f8940004c85a2db708
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637334"
---
# <a name="compiler-warning-level-1-c4358"></a>コンパイラの警告 (レベル 1) C4358

'operator': 戻り値の複合デリゲートの型が 'void';返される値が定義されていません

2 つのデリゲートを結合されましたが、戻り値は void ではありません。 非 void の戻り値を持つ 2 つのデリゲートを組み合わせると場合、コンパイラは、デリゲートの戻り値が使用されている場合、適切な割り当てを実行できません。

次の例では、C4358 が生成されます。

```
// C4358.cpp
// compile with: /clr /W1
delegate int D();
delegate void E();

ref class X {
   int i;
public:
   X(int ii) : i(ii) {}
   int f() {
      return i;
   }
};

ref class Y {
   int i;
public:
   Y() {}
   void g() {}
};

int main() {
   D^ d = gcnew D(gcnew X(1), &X::f);
   D^ d2 = gcnew D(gcnew X(2), &X::f);

   d += d2;   // C4358
   int j = d();   // return value indeterminate

   E^ e = gcnew E(gcnew Y, &Y::g);
   E^ e2 = gcnew E(gcnew Y, &Y::g);
   e += e2;   // OK
}
```