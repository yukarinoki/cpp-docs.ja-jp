---
title: コンパイラ エラー C2247
ms.date: 11/04/2016
f1_keywords:
- C2247
helpviewer_keywords:
- C2247
ms.assetid: 72efa03e-615e-4ef9-aede-0a98654b20fd
ms.openlocfilehash: ab1f83e2075128441cbffd2d939e3b99b45be4c3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596432"
---
# <a name="compiler-error-c2247"></a>コンパイラ エラー C2247

' identifier' の 'class' では、'specifier' を使用して、'class' から継承するためにアクセスできません。

`identifier` プライベートまたはプロテクトのアクセスで宣言されたクラスから継承されます。

次の例では、C2247 が生成されます。

```
// C2247.cpp
class A {
public:
   int i;
};
class B : private A {};    // B inherits a private A
class C : public B {} c;   // so even though C's B is public
int j = c.i;               // C2247, i not accessible
```

このエラーは、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成することもできます。 保護されたメンバーのアクセスを制御します。 プロテクト メンバー (n) は、(A) (n) がメンバーである、クラスから継承するクラス (B) のメンバー関数でのみアクセスできます。

コードは、Visual Studio .NET 2003 と Visual Studio .NET のバージョンの Visual C の両方で有効で、メンバーの型のフレンドを宣言します。 パブリック継承も使用されます。

```
// C2247b.cpp
// compile with: /c
// C2247 expected
class A {
public:
   void f();
   int n;
};

class B: protected A {
   // Uncomment the following line to resolve.
   // friend void A::f();
};

void A::f() {
   B b;
   b.n;
}
```

C2247 は、Visual Studio .NET 2003 で行ったコンパイラ準拠作業の結果として生成することもできます。 プライベート基本クラスはアクセスできないようになりました。 プライベート基底クラス型であるクラス (A) は (B) は (C) の基本クラスとして B を使用する型にアクセスできません。

コードは、Visual Studio .NET 2003 と Visual Studio .NET のバージョンの Visual C の両方で有効で、スコープ演算子を使用します。

```
// C2247c.cpp
// compile with: /c
struct A {};

struct B: private A {};

struct C : B {
   void f() {
      A *p1 = (A*) this;   // C2247
      // try the following line instead
      // ::A *p2 = (::A*) this;
   }
};
```