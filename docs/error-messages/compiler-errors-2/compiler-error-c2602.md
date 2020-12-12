---
description: 詳細については、「コンパイラエラー C2602」を参照してください。
title: コンパイラエラー C2602
ms.date: 11/04/2016
f1_keywords:
- C2602
helpviewer_keywords:
- C2602
ms.assetid: 6c07a40e-537e-4954-b5c5-1e0e58fe1952
ms.openlocfilehash: 2922ee0d35dd5820e1df23d9bc812c0650501b35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312022"
---
# <a name="compiler-error-c2602"></a>コンパイラエラー C2602

' class:: Identifier ' は ' class ' の基底クラスのメンバーではありません

`Identifier` 基底クラスから継承されたメンバーではないため、にアクセスできません。

次の例では、C2602 が生成されます。

```cpp
// C2602.cpp
// compile with: /c
struct X {
   int x;
};
struct A {
   int a;
};
struct B : public A {
   X::x;   // C2602 B is not derived from X
   A::a;   // OK
};
```
