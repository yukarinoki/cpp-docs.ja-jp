---
title: コンパイラ エラー C2680
ms.date: 11/04/2016
f1_keywords:
- C2680
helpviewer_keywords:
- C2680
ms.assetid: d6f7129e-dd17-4661-b680-18d6b925b1cc
ms.openlocfilehash: 7a0f58ae16baee00a86038c633f996a7d27a1019
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443434"
---
# <a name="compiler-error-c2680"></a>コンパイラ エラー C2680

'type': 無効なターゲットの型名

キャスト演算子はポインターまたは参照ではない型に変換しようとしました。 [Dynamic_cast](../../cpp/dynamic-cast-operator.md)演算子はポインターまたは参照に対してのみ使用できます。

次の例では、C2680 が生成されます。

```
// C2680.cpp
// compile with: /c
class A { virtual void f(); };
class B : public A {};

void g(B b) {
   A a;
   a = dynamic_cast<A>(b);   // C2680  target not a reference type
   a = dynamic_cast<A&>(b);   // OK
}
```

C2680 は、ターゲットが定義されていない場合にも発生します。

```
// C2680b.cpp
// compile with: /clr /c
// C2680 expected
using namespace System::Collections;

// Delete the following line to resolve.
ref class A;   // not defined

// Uncomment the following line to resolve.
// ref class A{};

public ref class B : ArrayList {
   property A^ C[int] {
      A^ get(int index) {
         return dynamic_cast<A^>(this->default::get(index));
      }
      void set(int index, A^ value) {
         this->default::set(index, value);
      }
   }
};
```