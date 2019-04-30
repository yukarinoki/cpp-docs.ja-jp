---
title: using 宣言
ms.date: 11/04/2016
helpviewer_keywords:
- using declaration
- declaring namespaces, unqualified names in namespaces
- declarations [C++], using-declaration
- namespaces [C++], unqualified names in
- using keyword [C++]
- declarations [C++], namespaces
ms.assetid: 4184e2b1-3adc-408e-b5f3-0b3f8b554723
ms.openlocfilehash: 46d8b1e13b55988efd40643482ffd6123034ccb5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403348"
---
# <a name="using-declaration"></a>using 宣言

宣言領域に名前を導入する宣言を使用して、宣言を使用して表示されます。

## <a name="syntax"></a>構文

```
using [typename] nested-name-specifier unqualified-id ;
using declarator-list ;
```

### <a name="parameters"></a>パラメーター

*入れ子になった名前子*スコープ解決演算子で終わる名前空間、クラス、または列挙型名とスコープ解決演算子 (:) のシーケンス。 1 つのスコープ解決演算子は、グローバル名前空間から名前を導入するために可能性があります。 キーワード**typename**は省略可能であり、基底クラスからクラス テンプレートに導入するときに、依存名を解決するのには使用できます。

*非修飾 id*修飾されていない id になる式識別子、オーバー ロードされた演算子名をユーザー定義リテラル演算子または変換関数名、クラスのデストラクター名、またはテンプレート名と引数リストがあります。

*宣言リスト*のコンマ区切りの一覧 **[typename]***入れ子になった名前子**修飾されていない id*宣言子、必要に応じて、その後に、省略記号。

## <a name="remarks"></a>Remarks

A エンティティのシノニムとして、非修飾名を導入する宣言を使用して別の場所を宣言します。 これにより、単一の名前が表示される宣言領域内の明示的な修飾せずに使用する特定の名前空間からです。 これとは対照的に、[ディレクティブを使用して](../cpp/namespaces-cpp.md#using_directives)、により*すべて*修飾なしで使用する名前空間内の名前。 **を使用して**キーワードも使用[エイリアスを入力](../cpp/aliases-and-typedefs-cpp.md)します。

## <a name="example"></a>例

using 宣言は、クラス定義で使用できます。

```cpp
// using_declaration1.cpp
#include <stdio.h>
class B {
public:
   void f(char) {
      printf_s("In B::f()\n");
   }

   void g(char) {
      printf_s("In B::g()\n");
   }
};

class D : B {
public:
   using B::f;    // B::f(char) is now visible as D::f(char)
   using B::g;    // B::g(char) is now visible as D::g(char)
   void f(int) {
      printf_s("In D::f()\n");
      f('c');     // Invokes B::f(char) instead of recursing
   }

   void g(int) {
      printf_s("In D::g()\n");
      g('c');     // Invokes B::g(char) instead of recursing
   }
};

int main() {
   D myD;
   myD.f(1);
   myD.g('a');
}
```

```Output
In D::f()
In B::f()
In B::g()
```

## <a name="example"></a>例

メンバーの宣言に使用する場合、using 宣言は基底クラスのメンバーを参照する必要があります。

```cpp
// using_declaration2.cpp
#include <stdio.h>

class B {
public:
   void f(char) {
      printf_s("In B::f()\n");
   }

   void g(char) {
      printf_s("In B::g()\n");
   }
};

class C {
public:
   int g();
};

class D2 : public B {
public:
   using B::f;   // ok: B is a base of D2
   // using C::g;   // error: C isn't a base of D2
};

int main() {
   D2 MyD2;
   MyD2.f('a');
}
```

```Output
In B::f()
```

## <a name="example"></a>例

使用して、使用して宣言されたメンバーの宣言は、明示的な修飾を使用して参照できます。 `::` プレフィックスは、グローバル名前空間を参照します。

```cpp
// using_declaration3.cpp
#include <stdio.h>

void f() {
   printf_s("In f\n");
}

namespace A {
   void g() {
      printf_s("In A::g\n");
   }
}

namespace X {
   using ::f;   // global f is also visible as X::f
   using A::g;   // A's g is now visible as X::g
}

void h() {
   printf_s("In h\n");
   X::f();   // calls ::f
   X::g();   // calls A::g
}

int main() {
   h();
}
```

```Output
In h
In f
In A::g
```

## <a name="example"></a>例

using 宣言を行うと、宣言によって作成されるシノニムは、using 宣言の時点で有効である定義のみを参照します。 using 宣言の後で名前空間に追加される定義は、無効なシノニムです。

によって定義された名前、**を使用して**宣言は、元の名前のエイリアスです。 using 宣言は元の宣言の型、リンケージ、またはその他の属性には影響しません。

```cpp
// post_declaration_namespace_additions.cpp
// compile with: /c
namespace A {
   void f(int) {}
}

using A::f;   // f is a synonym for A::f(int) only

namespace A {
   void f(char) {}
}

void f() {
   f('a');   // refers to A::f(int), even though A::f(char) exists
}

void b() {
   using A::f;   // refers to A::f(int) AND A::f(char)
   f('a');   // calls A::f(char);
}
```

## <a name="example"></a>例

名前空間内の関数では、1 つの名前のローカル宣言と using 宣言が同じスコープ内にある場合、それらはすべて同じエンティティ、つまり関数を参照している必要があります。

```cpp
// functions_in_namespaces1.cpp
// C2874 expected
namespace B {
    int i;
    void f(int);
    void f(double);
}

void g() {
    int i;
    using B::i;   // error: i declared twice
    void f(char);
    using B::f;   // ok: each f is a function
}
```

この例では、`using B::i` ステートメントにより、2 つ目の `int i` が `g()` 関数で宣言されます。 `using B::f` 内に定義された関数名に異なるパラメーター型があるため、`f(char)` ステートメントと `B::f` 関数は競合しません。

## <a name="example"></a>例

ローカル関数宣言は、using 宣言で定義された関数と同じ名前および型を含むことはできません。 例えば:

```cpp
// functions_in_namespaces2.cpp
// C2668 expected
namespace B {
    void f(int);
    void f(double);
}

namespace C {
    void f(int);
    void f(double);
    void f(char);
}

void h() {
    using B::f;          // introduces B::f(int) and B::f(double)
    using C::f;          // C::f(int), C::f(double), and C::f(char)
    f('h');              // calls C::f(char)
    f(1);                // C2668 ambiguous: B::f(int) or C::f(int)?
    void f(int);         // C2883 conflicts with B::f(int) and C::f(int)
}
```

## <a name="example"></a>例

継承では、using 宣言で基底クラスの名前を派生クラスのスコープ内に定義すると、派生クラスのメンバー関数によって、基底クラスで同じ名前と引数の型を持つ仮想メンバー関数がオーバーライドされます。

```cpp
// using_declaration_inheritance1.cpp
#include <stdio.h>
struct B {
   virtual void f(int) {
      printf_s("In B::f(int)\n");
   }

   virtual void f(char) {
      printf_s("In B::f(char)\n");
   }

   void g(int) {
      printf_s("In B::g\n");
   }

   void h(int);
};

struct D : B {
   using B::f;
   void f(int) {   // ok: D::f(int) overrides B::f(int)
      printf_s("In D::f(int)\n");
   }

   using B::g;
   void g(char) {   // ok: there is no B::g(char)
      printf_s("In D::g(char)\n");
   }

   using B::h;
   void h(int) {}   // Note: D::h(int) hides non-virtual B::h(int)
};

void f(D* pd) {
   pd->f(1);     // calls D::f(int)
   pd->f('a');   // calls B::f(char)
   pd->g(1);     // calls B::g(int)
   pd->g('a');   // calls D::g(char)
}

int main() {
   D * myd = new D();
   f(myd);
}
```

```Output
In D::f(int)
In B::f(char)
In B::g
In D::g(char)
```

## <a name="example"></a>例

using 宣言で定義された名前のすべてのインスタンスはアクセス可能である必要があります。 特に、派生クラスが基底クラスのメンバーにアクセスするために using 宣言を使用する場合は、そのメンバー名がアクセス可能である必要があります。 名前がオーバーロードされたメンバー関数の名前である場合、その名前のすべての関数にアクセス可能である必要があります。

メンバーのアクセシビリティの詳細については、次を参照してください。[メンバー アクセス コントロール](../cpp/member-access-control-cpp.md)します。

```cpp
// using_declaration_inheritance2.cpp
// C2876 expected
class A {
private:
   void f(char);
public:
   void f(int);
protected:
   void g();
};

class B : public A {
   using A::f;   // C2876: A::f(char) is inaccessible
public:
   using A::g;   // B::g is a public synonym for A::g
};
```

## <a name="see-also"></a>関連項目

[名前空間](../cpp/namespaces-cpp.md)<br/>
[キーワード](../cpp/keywords-cpp.md)