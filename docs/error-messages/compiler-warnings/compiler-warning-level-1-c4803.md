---
description: '詳細情報: コンパイラの警告 (レベル 1) C4803'
title: コンパイラの警告 (レベル 1) C4803
ms.date: 11/04/2016
f1_keywords:
- C4803
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
ms.openlocfilehash: 95646895133febbf03750d1b7a07d3a8141b6eff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334927"
---
# <a name="compiler-warning-level-1-c4803"></a>コンパイラの警告 (レベル 1) C4803

' method ': raise メソッドは、イベント ' event ' とは異なるストレージクラスを持っています。

イベントメソッドは、イベント宣言と同じストレージクラスを持つ必要があります。 コンパイラは、ストレージクラスが同じになるように、イベントのメソッドを調整します。

この警告は、インターフェイスからイベントを実装するクラスがある場合に発生する可能性があります。 コンパイラは、インターフェイスでイベントの raise メソッドを暗黙的に生成しません。 クラスにそのインターフェイスを実装すると、コンパイラは、raise メソッドを暗黙的に生成します。そのため、このメソッドは仮想にならず、警告が発生します。 イベントの詳細については、「 [event](../../extensions/event-cpp-component-extensions.md)」を参照してください。

警告をオフにする方法については、「 [warning](../../preprocessor/warning.md) プラグマ」を参照してください。

## <a name="example"></a>例

次の例では、C4803 が生成されます。

```cpp
// C4803.cpp
// compile with: /clr /W1
using namespace System;

public delegate void Del();

ref struct E {
   Del ^ _pd1;
   event Del ^ E1 {
      void add (Del ^ pd1) {
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));
      }

      void remove(Del^ pd1) {
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));
      }

      virtual void raise() {   // C4803 warning (remove virtual)
         if (_pd1)
            _pd1();
      }
   }

   void func() {
      Console::WriteLine("In E::func()");
   }
};

int main() {
   E ^ ep = gcnew E;
   ep->E1 += gcnew Del(ep, &E::func);
   ep->E1();
   ep->E1 -= gcnew Del(ep, &E::func);
   ep->E1();
}
```
