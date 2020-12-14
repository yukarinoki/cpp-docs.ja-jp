---
description: 詳細については、「コンパイラエラー C2280」を参照してください。
title: コンパイラエラー C2280
ms.date: 04/25/2017
f1_keywords:
- C2280
helpviewer_keywords:
- C2280
ms.assetid: e6c5b1fb-2b9b-4554-8ff9-775eeb37161b
ms.openlocfilehash: 74ed554006faa20046571971e080e0c0a2054b72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295056"
---
# <a name="compiler-error-c2280"></a>コンパイラエラー C2280

'*宣言*': 削除された関数を参照しようとしています

コンパイラは、関数を参照しようとしました `deleted` 。 このエラーは、ソースコード内でとして明示的にマークされているメンバー関数の呼び出しによって発生することがあり `= deleted` ます。 このエラーは、自動的に宣言され、コンパイラによってマークされる構造体またはクラスの暗黙的な特殊メンバー関数を呼び出すことによって発生することもあり `deleted` ます。 コンパイラが自動的にまたは特殊なメンバー関数を生成する場合の詳細について **`default`** は `deleted` 、「 [特殊なメンバー関数](../../cpp/special-member-functions.md)」を参照してください。

## <a name="example-explicitly-deleted-functions"></a>例: 明示的に削除された関数

明示的な関数を呼び出すと、 `deleted` このエラーが発生します。 明示的な `deleted` メンバー関数は、クラスまたは構造体が使用できないように意図的に設計されていることを意味します。そのため、この問題を解決するには、コードを変更して回避する必要があります。

```cpp
// C2280_explicit.cpp
// compile with: cl /c /W4 C2280_explicit.cpp
struct A {
    A();
    A(int) = delete;
};

struct B {
    A a1;
    A a2 = A(3); // C2280, calls deleted A::A(int)
    // To fix, remove the call to A(int)
};

void f() {
    B b;    // calls implicit B::B(void)
}
```

## <a name="example-uninitialized-data-members"></a>例: 初期化されていないデータメンバー

初期化されていない参照型のデータメンバーまたは **`const`** データメンバーにより、コンパイラは既定のコンストラクターを暗黙的に宣言し `deleted` ます。 この問題を解決するには、宣言時にデータメンバーを初期化します。

```cpp
// C2280_uninit.cpp
// compile with: cl /c C2280_uninit.cpp
struct A {
    const int i; // uninitialized const-qualified data
    // members or reference type data members cause
    // the implicit default constructor to be deleted.
    // To fix, initialize the value in the declaration:
    // const int i = 42;
} a;    // C2280
```

## <a name="example-reference-and-const-data-members"></a>例: 参照データメンバーと const データメンバー

**`const`** 参照型または参照型のデータメンバーによって、コンパイラによって `deleted` コピー代入演算子が宣言されます。 初期化されると、これらのメンバーをに割り当てることができないため、単純なコピーや移動は機能しません。 この問題を解決するには、エラーの原因となった割り当て操作を削除するようにロジックを変更することをお勧めします。

```cpp
// C2280_ref.cpp
// compile with: cl /c C2280_ref.cpp
extern int k;
struct A {
    A();
    int& ri = k; // a const or reference data member causes
    // implicit copy assignment operator to be deleted.
};

void f() {
    A a1, a2;
    // To fix, consider removing this assignment.
    a2 = a1;    // C2280
}
```

## <a name="example-movable-deletes-implicit-copy"></a>例: 移動可能な削除の暗黙的なコピー

クラスで移動コンストラクターまたは移動代入演算子が宣言されているが、コピーコンストラクターを明示的に宣言していない場合、コンパイラは暗黙的にコピーコンストラクターを宣言し、それをとして定義し `deleted` ます。 同様に、クラスが移動コンストラクターまたは移動代入演算子を宣言していても、コピー代入演算子を明示的に宣言していない場合、コンパイラは暗黙的にコピー代入演算子を宣言し、として定義し `deleted` ます。 この問題を解決するには、これらのメンバーを明示的に宣言する必要があります。

との接続にエラー C2280 が表示される場合 `unique_ptr` 、そのコピーコンストラクターを呼び出そうとしているため、ほぼ確実に `deleted` 機能します。 仕様により、を `unique_ptr` コピーすることはできません。 代わりに、移動コンストラクターを使用して所有権を譲渡します。

```cpp
// C2280_move.cpp
// compile with: cl /c C2280_move.cpp
class base
{
public:
    base();
    ~base();
    base(base&&);
    // Move constructor causes copy constructor to be
    // implicitly declared as deleted. To fix this
    // issue, you can explicitly declare a copy constructor:
    // base(base&);
    // If you want the compiler default version, do this:
    // base(base&) = default;
};

void copy(base *p)
{
    base b{*p};  // C2280
}
```

## <a name="example-variant-and-volatile-members"></a>例: バリアントメンバーと volatile メンバー

Visual Studio 2015 Update 2 より前のバージョンのコンパイラは、非準拠で、匿名共用体の既定のコンストラクターとデストラクターが生成されました。 これらは、として暗黙的に宣言されるようになりました `deleted` 。 また、これらのバージョン **`default`** **`default`** では、メンバー変数を持つクラスと構造体のコピーコンストラクターと移動コンストラクター、およびコピーおよび移動代入演算子の非準拠の暗黙的な定義も許可されて **`volatile`** います。 コンパイラは、これらを自明なコンストラクターと代入演算子を持つものと見なし、実装を生成しません **`default`** 。 このようなクラスが共用体のメンバー、またはクラス内の無名共用体のメンバーである場合、共用体またはクラスのコピーおよび移動のコンストラクターおよびコピーおよび移動代入演算子は、暗黙的にとして定義され `deleted` ます。 この問題を解決するには、必要な特殊なメンバー関数を明示的に宣言する必要があります。

```cpp
// C2280_variant.cpp
// compile with: cl /c C2280_variant.cpp
struct A {
    A() = default;
    A(const A&);
};

struct B {
    union {
        A a;
        int i;
    };
    // To fix this issue, declare the required
    // special member functions:
    // B();
    // B(const B& b);
};

int main() {
    B b1;
    B b2(b1);  // C2280
}
```

## <a name="example-indirect-base-members-deleted"></a>例: 間接的な基本メンバーが削除されました

Visual Studio 2015 Update 2 より前のバージョンでは、派生クラスは間接的に派生した基底クラスの特殊なメンバー関数を呼び出すことができました `private virtual` 。 コンパイラは、このような呼び出しが行われたときにコンパイラエラー C2280 を発行するようになりました。

この例では、クラスは `top` プライベート仮想から間接的に派生 `base` しています。 準拠しているコードでは、これにより、のメンバーは `base` にアクセスできなくなり `top` ます。型のオブジェクトを `top` 既定で構築または破棄することはできません。 以前のコンパイラの動作に依存するコードでこの問題を解決するには、派生を使用するように中間クラスを変更する `protected virtual` か、 `top` 直接派生を使用するようにクラスを変更します。

```cpp
// C2280_indirect.cpp
// compile with: cl /c C2280_indirect.cpp
class base
{
protected:
    base();
    ~base();
};

class middle : private virtual base {};
// Possible fix: Replace line above with:
// class middle : protected virtual base {};
class top : public virtual middle {};    // C4594, C4624
// Another possible fix: use direct derivation:
// class top : public virtual middle, private virtual base {};

void destroy(top *p)
{
    delete p;  // C2280
}
```
