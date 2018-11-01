---
title: コンパイラ エラー C3739
ms.date: 11/04/2016
f1_keywords:
- C3739
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
ms.openlocfilehash: 34f035c089b183670e87a23eb62f995b2af23c9b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567493"
---
# <a name="compiler-error-c3739"></a>コンパイラ エラー C3739

'class': event_receiver の 'layout_dependent' パラメーターが true の場合にのみ、構文がサポート

イベントの全体のインターフェイスをフックするしようとしましたが、`layout_dependent`で[event_receiver](../../windows/event-receiver.md)属性が true ではありません。 一度に 1 つのイベントをフックする必要があります。

次の例では、C3739 が生成されます。

```
// C3739.cpp
struct A
{
   __event void e();
};

// event_receiver is implied
// [ event_receiver(layout_dependent=false)]

// use the following line instead
// [event_receiver(com, layout_dependent=true), coclass ]
struct B
{
   void f();
   B(A* a)
   {
      __hook(A, a, &B::f);   // C3739
      // use the following line instead to hook a single event
      // __hook(&A::e, a, &B::f);
   }
};

int main()
{
}
```