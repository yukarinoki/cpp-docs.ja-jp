---
description: 詳細については、「コンパイラエラー C2276」を参照してください。
title: コンパイラ エラー C2276
ms.date: 11/04/2016
f1_keywords:
- C2276
helpviewer_keywords:
- C2276
ms.assetid: 62005ad9-6cb9-4b1f-965d-b875adaf695e
ms.openlocfilehash: dc6a407110ee121444b7e767f43d7d29ba42db72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134512"
---
# <a name="compiler-error-c2276"></a>コンパイラ エラー C2276

' operator ': バインドされたメンバー関数式に対する無効な操作です。

コンパイラにより、メンバーへのポインターを作成する構文に問題が見つかりました。

次の例では、C2276 が生成されます。

```cpp
// C2276.cpp
class A {
public:
   int func(){return 0;}
} a;

int (*pf)() = &a.func;   // C2276
// try the following line instead
// int (A::*pf3)() = &A::func;

class B {
public:
   void mf() {
      &this -> mf;   // C2276
      // try the following line instead
      // &B::mf;
   }
};

int main() {
   A a;
   &a.func;   // C2276
   // try the following line instead
   // &A::func;
}
```
