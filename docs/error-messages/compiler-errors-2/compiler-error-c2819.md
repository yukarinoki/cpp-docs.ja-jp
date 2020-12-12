---
description: 詳細については、「コンパイラエラー C2819」を参照してください。
title: コンパイラ エラー C2819
ms.date: 11/04/2016
f1_keywords:
- C2819
helpviewer_keywords:
- C2819
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
ms.openlocfilehash: fa30432399913c6bdd00bb2728931d213c14064c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194749"
---
# <a name="compiler-error-c2819"></a>コンパイラ エラー C2819

型 ' type ' にオーバーロードされたメンバー ' operator-> ' がありません

`operator->()`このポインター操作を使用するには、を定義する必要があります。

次の例では、C2819 が生成されます。

```cpp
// C2819.cpp
// compile with: /c
class A {
   public:
      int i;
};

class B {};

void C(B j) {
   j->i;   // C2819
}

class D {
   A* pA;

   public:
      A* operator->() {
         return pA;
      }
};

void F(D j) {
   j->i;
}
```

C2819 は [、参照型に C++ スタックセマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)を使用する場合にも発生する可能性があります。 次の例では、C2819 が生成されます。

```cpp
// C2819_b.cpp
// compile with: /clr
ref struct R {
   void Test() {}
};

int main() {
   R r;
   r->Test();   // C2819
   r.Test();   // OK
}
```
