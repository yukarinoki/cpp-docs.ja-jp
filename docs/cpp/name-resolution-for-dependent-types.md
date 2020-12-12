---
description: 詳細については、「依存型の名前解決」を参照してください。
title: 依存する型の名前解決
ms.date: 11/04/2016
ms.assetid: 34066bb4-0c79-4fd8-bda7-539a60a277ab
ms.openlocfilehash: f50b067062f01d04ce26374ad969d572e1a7fe08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313789"
---
# <a name="name-resolution-for-dependent-types"></a>依存する型の名前解決

テンプレート定義内の修飾名にを使用して、 **`typename`** 指定された修飾名が型を識別することをコンパイラに伝えます。 詳細については、「 [typename](../cpp/typename.md)」を参照してください。

```cpp
// template_name_resolution1.cpp
#include <stdio.h>
template <class T> class X
{
public:
   void f(typename T::myType* mt) {}
};

class Yarg
{
public:
   struct myType { };
};

int main()
{
   X<Yarg> x;
   x.f(new Yarg::myType());
   printf("Name resolved by using typename keyword.");
}
```

```Output
Name resolved by using typename keyword.
```

依存名の名前参照によって、テンプレート定義のコンテキストの名前が検証されます。次の例では、このコンテキストでは、 `myFunction(char)` テンプレートのインスタンス化のコンテキストが検索されます。次の例では、テンプレートは main でインスタンス化されています。したがって、は、 `MyNamespace::myFunction` インスタンス化の時点から参照でき、より良い一致として選択されます。 `MyNamespace::myFunction` の名前を変更した場合、`myFunction(char)` が代わりに呼び出されます。

すべての名前は依存名のように解決されます。 いずれにしても、名前の衝突が発生する可能性がある場合は、完全修飾名を使用することをお勧めします。

```cpp
// template_name_resolution2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;

void myFunction(char)
{
   cout << "Char myFunction" << endl;
}

template <class T> class Class1
{
public:
   Class1(T i)
   {
      // If replaced with myFunction(1), myFunction(char)
      // will be called
      myFunction(i);
}
};

namespace MyNamespace
{
   void myFunction(int)
   {
      cout << "Int MyNamespace::myFunction" << endl;
   }
};

using namespace MyNamespace;

int main()
{
   Class1<int>* c1 = new Class1<int>(100);
}
```

### <a name="output"></a>出力

```Output
Int MyNamespace::myFunction
```

### <a name="template-disambiguation"></a>テンプレートのあいまいさの解消

Visual Studio 2012 では、"template" キーワードを使用してあいまいさを解消するために、C++ 98/03/11 の標準規則が適用されます。 次の例では、一致しない行と準拠している行の両方を Visual Studio 2010 が受け入れます。  Visual Studio 2012 では、準拠している行のみが受け入れられます。

```cpp
#include <iostream>
#include <ostream>
#include <typeinfo>
using namespace std;

template <typename T> struct Allocator {
    template <typename U> struct Rebind {
        typedef Allocator<U> Other;
    };
};

template <typename X, typename AY> struct Container {
    #if defined(NONCONFORMANT)
        typedef typename AY::Rebind<X>::Other AX; // nonconformant
    #elif defined(CONFORMANT)
        typedef typename AY::template Rebind<X>::Other AX; // conformant
    #else
        #error Define NONCONFORMANT or CONFORMANT.
    #endif
};

int main() {
    cout << typeid(Container<int, Allocator<float>>::AX).name() << endl;
}
```

あいまいさを解消する規則に準拠している必要があるのは、既定で、C++ は `AY::Rebind` がテンプレートでないと仮定し、そのためコンパイラは次の "`<`" を "より小さい" と解釈するためです。 "`Rebind`" を山かっことして正しく解析できるように、`<` がテンプレートであることを知っている必要があります。

## <a name="see-also"></a>関連項目

[名前解決](../cpp/templates-and-name-resolution.md)
