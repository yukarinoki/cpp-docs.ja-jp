---
description: 詳細については、「コンパイラエラー C3206」を参照してください。
title: コンパイラ エラー C3206
ms.date: 11/04/2016
f1_keywords:
- C3206
helpviewer_keywords:
- C3206
ms.assetid: d62995b5-e349-4418-bbe8-8a5e776ca7b0
ms.openlocfilehash: ea4ded5daebe0f002a3d0363fba125c2c02f332b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174014"
---
# <a name="compiler-error-c3206"></a>コンパイラ エラー C3206

'function': 'param' の型引数が無効です。クラス型 'typename' の型引数リストがありません

テンプレート関数は、テンプレート型引数を取るものと定義されています。 しかし、テンプレート template 引数が渡されました。

次の例では C3206 が生成されます。

```cpp
// C3206.cpp
template <class T>
void f() {}

template <class T>
struct S {};

void f1() {
   f<S>();   // C3206
   // try the following line instead
   // f<S<int> >();
}
```

考えられる解決策:

```cpp
// C3206b.cpp
// compile with: /c
template <class T>
void f() {}

template <class T>
struct S {};

void f1() {
   f<S<int> >();
}
```

C3206 は、ジェネリックを使用しているときも発生します。

```cpp
// C3206c.cpp
// compile with: /clr
generic <class GT1>
void gf() {}

generic <class T>
value struct GS {};

int main() {
   gf<GS>();   // C3206
}
```

考えられる解決策:

```cpp
// C3206d.cpp
// compile with: /clr
generic <class GT1>
void gf() {}

generic <class T>
value struct GS {};

int main() {
   gf<GS<int> >();
}
```

クラス テンプレートは、テンプレート型引数として許可されません。 次の例では、C3206 が発生します。

```cpp
// C3206e.cpp
template <class T>
struct S {};

template <class T>
void func() {   // takes a type
   T<int> t;
}

int main() {
   func<S>();   // C3206 S is not a type.
}
```

考えられる解決策:

```cpp
// C3206f.cpp
template <class T>
struct S {};

template <class T>
void func() {   // takes a type
   T t;
}

int main() {
   func<S<int> >();
}
```

テンプレートテンプレートパラメーターが必要な場合は、テンプレートテンプレートパラメーターを受け取るテンプレートクラスに関数をラップする必要があります。

```cpp
// C3206g.cpp
template <class T>
struct S {};

template<template<class> class TT>
struct X {
   static void func() {
      TT<int> t1;
      TT<char> t2;
   }
};

int main() {
   X<S>::func();
}
```
