---
title: コンパイラ エラー C3240
ms.date: 11/04/2016
f1_keywords:
- C3240
helpviewer_keywords:
- C3240
ms.assetid: 1a8dc213-b80c-47ae-ada0-e9554b635d1e
ms.openlocfilehash: a8334b4f95ccadcce73a79d787669cba9f911199
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504612"
---
# <a name="compiler-error-c3240"></a>コンパイラ エラー C3240

'function': 'type' のオーバー ロードされていない抽象メンバー関数でなければなりません

基本データ型には、定義された関数が含まれています。 関数は仮想である必要があります。

## <a name="example"></a>例

次の例では、C3240 が生成されます。

```
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