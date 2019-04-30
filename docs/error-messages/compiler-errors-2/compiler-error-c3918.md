---
title: コンパイラ エラー C3918
ms.date: 11/04/2016
f1_keywords:
- C3918
helpviewer_keywords:
- C3918
ms.assetid: a8b3a90a-3fe1-4244-a5ff-a31cdae97d98
ms.openlocfilehash: 2c2d2f2598d06ca228a96f2786fcb02888e29a1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386617"
---
# <a name="compiler-error-c3918"></a>コンパイラ エラー C3918

使用するにはデータ メンバー ' member' には

C3918 は、イベントに関連するいくつかの理由で発生します。

## <a name="example"></a>例

C3918 は、クラスのメンバーは、現在のコンテキストで必要な場合に発生します。 次の例では、C3918 が生成されます。

```
// C3918.cpp
// compile with: /clr /c
public ref class C {
public:
   System::Object ^ o;
   delegate void Del();

   event Del^ MyEvent {
      void add(Del^ev) {
         if ( MyEvent != nullptr) {}   // C3918
         if ( o != nullptr) {}   // OK
   }
   void remove(Del^){}
   }
};
```

## <a name="example"></a>例

C3918 は、null (イベント名が提供されなくへの直接アクセスにバッキング ストアのデリゲートをイベントの) 単純なイベントを確認しようとする場合にも発生します。

次の例では、C3918 が生成されます。

```
// C3918_2.cpp
// compile with: /clr /c
using namespace System;
public delegate int MyDel(int);

interface struct IEFace {
   event MyDel ^ E;
};

ref struct EventSource : public IEFace {
   virtual event MyDel ^ E;
   void Fire_E(int i) {
      if (E)   // C3918
         E(i);
   }
};
```

## <a name="example"></a>例

C3918 が正しくないイベントにサブスクライブする場合にも発生します。 次の例では、C3918 が生成されます。

```
// C3918_3.cpp
// compile with: /clr /c
using namespace System;

public delegate void del();

public ref class A {
public:
   event del^ e {
      void add(del ^handler ) {
         d += handler;
      }

      void remove(del ^handler) {
         d -= handler;
      }

      void raise() {
         d();
      }
   }

   del^ d;
   void f() {}

   A() {
      e = gcnew del(this, &A::f);   // C3918
      // try the following line instead
      // e += gcnew del(this, &A::f);
      e();
   }
};

int main() {
   A a;
}
```