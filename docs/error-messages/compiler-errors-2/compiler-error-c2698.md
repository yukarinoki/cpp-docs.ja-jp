---
description: 詳細については、「コンパイラエラー C2698」を参照してください。
title: コンパイラエラー C2698
ms.date: 11/04/2016
f1_keywords:
- C2698
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
ms.openlocfilehash: a787c43e7a885734f4c6a2d76aa16d51e19615c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326631"
---
# <a name="compiler-error-c2698"></a>コンパイラエラー C2698

' 宣言 1 ' の using 宣言は、' 宣言 2 ' の既存の using 宣言と共存することはできません

データメンバーに [using 宣言](../../cpp/using-declaration.md) を使用すると、同じ名前を使用する同じスコープ内のすべての using 宣言は許可されません。これは、関数だけがオーバーロードされるためです。

次の例では、C2698 が生成されます。

```cpp
// C2698.cpp
struct A {
   int x;
};

struct B {
   int x;
};

struct C : A, B {
   using A::x;
   using B::x;   // C2698
}
```
