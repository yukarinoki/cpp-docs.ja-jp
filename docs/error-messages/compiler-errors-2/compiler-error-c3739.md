---
description: 詳細については、「コンパイラエラー C3739」を参照してください。
title: コンパイラ エラー C3739
ms.date: 11/04/2016
f1_keywords:
- C3739
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
ms.openlocfilehash: dd08b171503d7c5c4c7d46b9d06d4372513e2e73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340295"
---
# <a name="compiler-error-c3739"></a>コンパイラ エラー C3739

' class ': 構文は、event_receiver の ' layout_dependent ' パラメーターが true の場合にのみサポートされます

イベントのインターフェイス全体をフックしようとしましたが、 `layout_dependent` [event_receiver](../../windows/attributes/event-receiver.md) 属性が true ではありません。一度に1つのイベントをフックする必要があります。

次の例では、C3739 が生成されます。

```cpp
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
