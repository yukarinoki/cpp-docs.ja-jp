---
title: 原始式
ms.date: 11/04/2016
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
ms.openlocfilehash: 03f0d0d04ad8ef2b052b9303d15437c53369a003
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177626"
---
# <a name="primary-expressions"></a>原始式

基本式は、より複雑な式のビルド ブロックです。 つまり、リテラル、名前、スコープ解決演算子 (`::`) で修飾された名前です。  基本式は次のいずれかの形式になります。

```
literal
this
name
::name ( expression )
```

*リテラル*は定数のプライマリ式です。 その型は、リテラルの指定の形式によって決まります。 リテラルの指定の詳細については、「[リテラル](../cpp/numeric-boolean-and-pointer-literals-cpp.md)」を参照してください。

**This**キーワードは、クラスオブジェクトへのポインターです。 非静的メンバー関数内で使用でき、その関数が呼び出されたクラスのインスタンスを参照します。 **この**キーワードは、クラスメンバー関数の本体の外側では使用できません。

**このポインター**の型は、**この**ポインターを特に変更していない関数内で、const (`type` はクラス名) **\*** `type` ます。 次の例では、メンバー関数の宣言と、**この**の型を示します。

```cpp
// expre_Primary_Expressions.cpp
// compile with: /LD
class Example
{
public:
    void Func();          //  * const this
    void Func() const;    //  const * const this
    void Func() volatile; //  volatile * const this
};
```

**この**ポインターの型を変更する方法の詳細については、[このポインター](this-pointer.md)を参照してください。

名前の前のスコープ解決演算子 (`::`) は基本式です。  そのような名前は、メンバー名ではなく、グローバル スコープでの名前であることが必要です。  この式の型は名前の宣言によって決まります。 宣言名が左辺値である場合は、左辺値 (代入演算子式の左辺になる式) です。 スコープ解決演算子を使用すると、グローバル名が現在のスコープでは隠されていても、その名前を参照できます。 スコープ解決演算子の使用方法の例については、「[スコープ](../cpp/scope-visual-cpp.md)」を参照してください。

かっこで囲まれた式も基本式であり、その型と値はかっこで囲まれていない式のものと一致します。 この式は、かっこで囲まれていない式が左辺値であれば、左辺値です。

次に示しているのは、基本式の例です。

```cpp
100 // literal
'c' // literal
this // in a member function, a pointer to the class instance
::func // a global function
::operator + // a global operator function
::A::B // a global qualified name
( i + 1 ) // a parenthesized expression
```

次の例では、さまざまな形式で、すべての*名前*と、主な式を示しています。

```cpp
MyClass // a identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>参照

[式の型](../cpp/types-of-expressions.md)
