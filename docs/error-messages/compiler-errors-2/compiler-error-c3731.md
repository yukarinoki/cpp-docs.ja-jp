---
title: コンパイラ エラー C3731
ms.date: 11/04/2016
f1_keywords:
- C3731
helpviewer_keywords:
- C3731
ms.assetid: 45f89fcd-464c-4bc8-8a42-edcb5416d26c
ms.openlocfilehash: 5acc33869648f83cd44bc557128c685f521ddf88
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496058"
---
# <a name="compiler-error-c3731"></a>コンパイラ エラー C3731

'function1' の互換性のないイベントとハンドラー 'function2';イベント ソースとイベント ハンドラーが同じ型にする必要があります。

イベント ソースとイベント レシーバーは、同じ型を持つ必要があります (たとえば`native`と`com`型)。 このエラーを修正するには、イベント ソースとイベント ハンドラーの一致の種類を確認します。

次の例では、C3731 が生成されます。

```
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