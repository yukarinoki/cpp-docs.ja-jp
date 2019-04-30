---
title: コンパイラ エラー C2910
ms.date: 11/04/2016
f1_keywords:
- C2910
helpviewer_keywords:
- C2910
ms.assetid: 09c50e6a-e099-42f6-8ed6-d80e292a7a36
ms.openlocfilehash: 58d56ad834b34425cda4ac7ba081eabd2424e451
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408356"
---
# <a name="compiler-error-c2910"></a>コンパイラ エラー C2910

'function': 明示的に特殊化することはできません

明示的に特殊化関数を 2 回の試行が検出されました。

次の例では、C2910 が生成されます。

```
// C2910.cpp
// compile with: /c
template <class T>
struct S;

template <> struct S<int> { void f() {} };
template <> void S<int>::f() {}   // C2910 delete this specialization
```

C2910 は、非テンプレートのメンバーを明示的に特殊化しようとする場合にも生成できます。 関数テンプレートをのみ明示的に特殊化することができます。

次の例では、C2910 が生成されます。

```
// C2910b.cpp
// compile with: /c
template <class T> struct A {
   A(T* p);
};

template <> struct A<void> {
   A(void* p);
};

template <class T>
inline A<T>::A(T* p) {}

template <> A<void>::A(void* p){}   // C2910
// try the following line instead
// A<void>::A(void* p){}
```

このエラーは Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成することも: です。

コードは、Visual Studio .NET 2003 と Visual Studio .NET のバージョンの Visual C では有効になります、削除`template <>`します。

次の例では、C2910 が生成されます。

```
// C2910c.cpp
// compile with: /c
template <class T> class A {
   void f();
};

template <> class A<int> {
   void f();
};

template <> void A<int>::f() {}   // C2910
// try the following line instead
// void A<int>::f(){}   // OK
```