---
description: 詳細については、「コンパイラエラー C3240」を参照してください。
title: コンパイラ エラー C3240
ms.date: 11/04/2016
f1_keywords:
- C3240
helpviewer_keywords:
- C3240
ms.assetid: 1a8dc213-b80c-47ae-ada0-e9554b635d1e
ms.openlocfilehash: a8e78e6bb846d96fc0087c3d02d1eb757a0586f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307367"
---
# <a name="compiler-error-c3240"></a>コンパイラ エラー C3240

' function ': ' type ' のオーバーロードされていない抽象メンバー関数でなければなりません

定義された関数が基本型に含まれています。 関数は仮想でなければなりません。

## <a name="example"></a>例

次の例では、C3240 が生成されます。

```cpp
// C3240.cpp
// compile with: /c
__interface I {
   void f();
};

struct A1 : I {
   void f() {}
};

struct A2 : I {
   void f() = 0;
};

template <class T>
struct A3 : T {
   void T::f() {}
};

template <class T>
struct A4 : T {
   void T::f() {}
};

A3<A1> x;   // C3240
A3<I> x2;
A4<A2> x3;
```
