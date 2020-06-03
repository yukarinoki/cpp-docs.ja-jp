---
title: 'スコープ解決演算子: ::'
ms.date: 11/04/2016
f1_keywords:
- '::'
helpviewer_keywords:
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- ':: operator'
ms.assetid: fd5de9d3-c716-4e12-bae9-03a16fd79a50
ms.openlocfilehash: 07c2884ed0ba114c22a0c71bbaf7268d6f6931a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178887"
---
# <a name="scope-resolution-operator-"></a>スコープ解決演算子: ::

スコープ解決演算子 **::** は、さまざまなスコープで使用される識別子を識別し、あいまいさを解消するために使用されます。 スコープの詳細については、「[スコープ](../cpp/scope-visual-cpp.md)」を参照してください。

## <a name="syntax"></a>構文

```
:: identifier
class-name :: identifier
namespace :: identifier
enum class :: identifier
enum struct :: identifier
```

## <a name="remarks"></a>解説

`identifier` は変数、関数、または列挙値になることがあります。

## <a name="with-classes-and-namespaces"></a>クラスと名前空間の使用

次の例は、スコープ解決演算子を名前空間およびクラスと共に使用する方法を示します。

```cpp
namespace NamespaceA{
    int x;
    class ClassA {
    public:
        int x;
    };
}

int main() {

    // A namespace name used to disambiguate
    NamespaceA::x = 1;

    // A class name used to disambiguate
    NamespaceA::ClassA a1;
    a1.x = 2;
}
```

スコープ修飾子を持たないスコープ解決演算子はグローバル名前空間を参照します。

```cpp
namespace NamespaceA{
    int x;
}

int x;

int main() {
    int x;

    // the x in main()
    x = 0;
    // The x in the global namespace
    ::x = 1;

    // The x in the A namespace
    NamespaceA::x = 2;
}
```

スコープ解決演算子は、名前空間のメンバーの特定、または using ディレクティブでメンバーの名前空間をノミネートする名前空間の特定に使用できます。 下の例では、名前空間 `NamespaceC` で `ClassB` が宣言されていた場合でも、`ClassB` を使用して `NamespaceB` を修飾できます。これは、`NamespaceB` が using ディレクティブにより `NamespaceC` でノミネートされているからです。

```cpp
namespace NamespaceB {
    class ClassB {
    public:
        int x;
    };
}

namespace NamespaceC{
    using namespace B;
}
int main() {
    NamespaceB::ClassB c_b;
    NamespaceC::ClassB c_c;

    c_b.x = 3;
    c_c.x = 4;
}
```

スコープ解決演算子のチェーンを使用できます。 次の例で、`NamespaceD::NamespaceD1` は入れ子になった名前空間 `NamespaceD1` を特定し、`NamespaceE::ClassE::ClassE1` は入れ子になったクラス `ClassE1` を特定します。

```cpp
namespace NamespaceD{
    namespace NamespaceD1{
        int x;
    }
}

namespace NamespaceE{
    class ClassE{
    public:
        class ClassE1{
        public:
            int x;
        };
    };
}

int main() {
    NamespaceD:: NamespaceD1::x = 6;
    NamespaceE::ClassE::ClassE1 e1;
    e1.x = 7  ;
}
```

## <a name="with-static-members"></a>静的メンバーの使用

スコープ解決演算子を使用してクラスの静的メンバーを呼び出すことができます。

```cpp
class ClassG {
public:
    static int get_x() { return x;}
    static int x;
};

int ClassG::x = 6;

int main() {

    int gx1 = ClassG::x;
    int gx2 = ClassG::get_x();
}
```

## <a name="with-scoped-enumerations"></a>スコープを持つ列挙型の使用

スコープ解決演算子は、次の例に示すように、スコープ列挙[列挙型の宣言](../cpp/enumerations-cpp.md)の値と共にも使用されます。

```cpp
enum class EnumA{
    First,
    Second,
    Third
};

int main() {
    EnumA enum_value = EnumA::First;
}
```

## <a name="see-also"></a>参照

[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[名前空間](../cpp/namespaces-cpp.md)
