---
title: 'スコープ解決演算子: `::`'
description: 標準 C++ でのスコープ解決演算子の動作について説明 `::` します。
ms.date: 12/06/2020
f1_keywords:
- '::'
helpviewer_keywords:
- scope, scope resolution operator
- operators [C++], scope resolution
- scope resolution operator
- ':: operator'
ms.openlocfilehash: ff774d9fcca9f68cb2925af82c55ef438ab4d71a
ms.sourcegitcommit: 7b131db4ed39bddb4a456ebea402f47c5cbd69d3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/07/2020
ms.locfileid: "96776532"
---
# <a name="scope-resolution-operator-"></a>スコープ解決演算子: `::`

スコープ解決演算子 **`::`** は、異なるスコープで使用される識別子を識別し、あいまいさを解消するために使用されます。 スコープの詳細については、「 [スコープ](../cpp/scope-visual-cpp.md)」を参照してください。

## <a name="syntax"></a>構文

> *`qualified-id`*:\
> &emsp; *`nested-name-specifier`* **`template`** <sub>opt</sub> *`unqualified-id`*

> *`nested-name-specifier`*:\
> &emsp;**`::`**\
> &emsp;*`type-name`* **`::`**\
> &emsp;*`namespace-name`* **`::`**\
> &emsp;*`decltype-specifier`* **`::`**\
> &emsp;*`nested-name-specifier`* *`identifier`* **`::`**\
> &emsp;*`nested-name-specifier`***`template`** <sub>opt</sub>選択 *`simple-template-id`***`::`**

> *`unqualified-id`*:\
> &emsp;*`identifier`*\
> &emsp;*`operator-function-id`*\
> &emsp;*`conversion-function-id`*\
> &emsp;*`literal-operator-id`*\
> &emsp;**`~`** *`type-name`*\
> &emsp;**`~`** *`decltype-specifier`*\
> &emsp;*`template-id`*

## <a name="remarks"></a>注釈

`identifier` は変数、関数、または列挙値になることがあります。

## <a name="use--for-classes-and-namespaces"></a>`::`クラスと名前空間に使用する

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

スコープ解決演算子を使用すると、のメンバーを識別し **`namespace`** たり、ディレクティブ内のメンバーの名前空間をノミネートする名前空間を識別したりできます **`using`** 。 次の例では、を使用して、が `NamespaceC` `ClassB` 名前空間で宣言されていてもを修飾でき `ClassB` `NamespaceB` ます。これは、が `NamespaceB` `NamespaceC` ディレクティブによって修飾されているため **`using`** です。

```cpp
namespace NamespaceB {
    class ClassB {
    public:
        int x;
    };
}

namespace NamespaceC{
    using namespace NamespaceB;
}

int main() {
    NamespaceB::ClassB b_b;
    NamespaceC::ClassB c_b;

    b_b.x = 3;
    c_b.x = 4;
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

## <a name="use--for-static-members"></a>`::`静的メンバーに使用する

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

## <a name="use--for-scoped-enumerations"></a>`::`スコープ列挙型に使用する

スコープ解決演算子は、次の例に示すように、スコープ列挙 [列挙型の宣言](../cpp/enumerations-cpp.md)の値と共にも使用されます。

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

## <a name="see-also"></a>関連項目

[C++ の組み込み演算子、優先順位、および結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[名前空間](../cpp/namespaces-cpp.md)
