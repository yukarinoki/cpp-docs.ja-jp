---
description: 詳細については、「コンパイラエラー C3731」を参照してください。
title: コンパイラ エラー C3731
ms.date: 11/04/2016
f1_keywords:
- C3731
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
ms.openlocfilehash: 8a7ad836083a8c103df7becd7605a0dfd0efeea7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245084"
---
# <a name="compiler-error-c3731"></a>コンパイラ エラー C3731

互換性のないイベント ' function1 ' とハンドラー ' function2 ';イベントソースとイベントハンドラーは同じ型でなければなりません

イベントソースとイベントレシーバーの型は同じである必要があります (例として、 `native` `com` 型など)。 このエラーを修正するには、イベントソースの型とイベントハンドラーが一致するようにします。

次の例では、C3731 が生成されます。

```cpp
// C3731.cpp
// compile with: /clr
#using <mscorlib.dll>
[event_source(native)]
struct A {
   __event void MyEvent();
};

[event_receiver(managed)]
// try the following line instead
// [event_receiver(native)]
struct B {
   void func();
   B(A a) {
      __hook(&A::MyEvent, &a, &B::func);   // C3731
   }
};

int main() {
}
```
