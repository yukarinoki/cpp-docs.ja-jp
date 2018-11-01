---
title: コンパイラ エラー C2875
ms.date: 11/04/2016
f1_keywords:
- C2875
helpviewer_keywords:
- C2875
ms.assetid: d589fc0c-08b2-4a79-bc0e-dca5eb80bdd5
ms.openlocfilehash: 59df226e2740dbda3a67e0c3c49d688a3e564fee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622860"
---
# <a name="compiler-error-c2875"></a>コンパイラ エラー C2875

使用して宣言をによって ':identifier' の複数の宣言

宣言は、2 回定義する同じ項目です。

次の例では、C2875 が生成されます。

```
// C2875.cpp
struct A {
   void f(int*);
};

struct B {
   void f(double*);
};

struct AB : A, B {
   using A::f;
   using A::f;   // C2875
   using B::f;
};
```