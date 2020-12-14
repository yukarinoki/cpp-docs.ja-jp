---
description: 詳細については、「コンパイラエラー C3637」を参照してください。
title: コンパイラ エラー C3637
ms.date: 11/04/2016
f1_keywords:
- C3637
helpviewer_keywords:
- C3637
ms.assetid: 72391377-8519-43d9-870a-73a6423deb74
ms.openlocfilehash: d62612778690984245d6b90fc1449177ec5f8d2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239208"
---
# <a name="compiler-error-c3637"></a>コンパイラ エラー C3637

' function ': フレンド関数の定義を関数型の特殊化として使用することはできません

フレンド関数がテンプレートまたはジェネリックに対して正しく定義されていません。

次の例では、C3637 が生成されます。

```cpp
// C3637.cpp
template <class T>
void f();

struct S {
   friend void f<int>() {}   // C3637
};
```

考えられる解決策:

```cpp
// C3637b.cpp
// compile with: /c
template <class T>
void f();

struct S {
   friend void f() {}
};
```

C3637 は、ジェネリックを使用する場合にも発生する可能性があります。

```cpp
// C3637c.cpp
// compile with: /clr

generic <class T>
void gf();

struct S {
   friend void gf<int>() {}   // C3637
};
```

考えられる解決策:

```cpp
// C3637d.cpp
// compile with: /clr /c
generic <class T>
void gf();

struct S {
   friend void gf() {}
};
```
