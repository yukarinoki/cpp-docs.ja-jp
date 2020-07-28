---
title: 非標準動作
ms.date: 05/06/2019
helpviewer_keywords:
- compatibility and compliance, nonstandard behavior
- Microsoft-specific, compiler behavior
- nonstandard behavior, compliance and compatibility
ms.assetid: a57dea27-dc79-4f64-8a83-017e84841773
ms.openlocfilehash: f31938c78e443bb53a286f79661d86b7a6e9edbc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87186543"
---
# <a name="nonstandard-behavior"></a>非標準動作

以下のセクションでは、c++ の Microsoft 実装が C++ 標準に準拠していない箇所をいくつか紹介します。 ここで示している節番号は C++ 11 規格 (ISO/IEC 14882:2011(E)) の節番号に対応しています。

C++ 標準で定義されているものとは異なるコンパイラの制限の一覧については、「[コンパイラの制限](../cpp/compiler-limits.md)」を指定します。

## <a name="covariant-return-types"></a>共変の戻り値の型

仮想関数が可変個の引数を持つ場合、仮想既定クラスは共変の戻り値の型としてサポートされません。 このことは C++ ISO 仕様の 10.3 節 7 項に準拠していません。 次のサンプルはコンパイルされず、コンパイラエラー [C2688](../error-messages/compiler-errors-2/compiler-error-c2688.md)が発生します。

```cpp
// CovariantReturn.cpp
class A
{
   virtual A* f(int c, ...);   // remove ...
};

class B : virtual A
{
   B* f(int c, ...);   // C2688 remove ...
};
```

## <a name="binding-nondependent-names-in-templates"></a>テンプレートの非依存名のバインド

現在、Microsoft C++ コンパイラでは、テンプレートを最初に解析するときに非依存の名前をバインドすることはサポートされていません。 このことは、C++ ISO 仕様の 14.6.3 節に準拠していません。 そのため、テンプレートの定義後 (ただしインスタンス化前) にオーバーロードが宣言される場合があります。

```cpp
#include <iostream>
using namespace std;

namespace N {
   void f(int) { cout << "f(int)" << endl;}
}

template <class T> void g(T) {
    N::f('a');   // calls f(char), should call f(int)
}

namespace N {
    void f(char) { cout << "f(char)" << endl;}
}

int main() {
    g('c');
}
// Output: f(char)
```

## <a name="function-exception-specifiers"></a>関数の例外指定子

`throw()` 以外の関数の例外の指定子は解析されますが、使用されません。 このことは、ISO C++ 仕様の 15.4 節に準拠していません。 次に例を示します。

```cpp
void f() throw(int); // parsed but not used
void g() throw();    // parsed and used
```

例外の指定の詳細については、「[例外の指定](../cpp/exception-specifications-throw-cpp.md)」を参照してください。

## <a name="char_traitseof"></a>char_traits::eof()

C++ 標準では、 [char_traits:: eof](../standard-library/char-traits-struct.md#eof)は、有効な値に対応していない必要があり `char_type` ます。 Microsoft C++ コンパイラは、型に対してこの制約を強制し **`char`** ますが、型には適用しません **`wchar_t`** 。 このことは、C++ ISO 規格の 12.1.1 節の表 62 に示された要件に準拠していません。 次に示しているのはその例です。

```cpp
#include <iostream>

int main()
{
    using namespace std;

    char_traits<char>::int_type int2 = char_traits<char>::eof();
    cout << "The eof marker for char_traits<char> is: " << int2 << endl;

    char_traits<wchar_t>::int_type int3 = char_traits<wchar_t>::eof();
    cout << "The eof marker for char_traits<wchar_t> is: " << int3 << endl;
}
```

## <a name="storage-location-of-objects"></a>オブジェクトの格納場所

C++ 規格の 1.8 節 6 項によると、完全な C++ オブジェクトには一意の格納場所が必要です。 ただし、Microsoft C++ では、データメンバーのない型が、オブジェクトの有効期間にわたって他の型とストレージの場所を共有する場合があります。
