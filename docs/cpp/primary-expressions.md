---
title: 基本式
description: C++ プログラミング言語の主な式。
ms.date: 10/02/2020
helpviewer_keywords:
- primary expressions
- expressions [C++], name
- expressions [C++], literal
- expressions [C++], primary
- expressions [C++], qualified names
ms.assetid: 8ef9a814-6058-4b93-9b6e-e8eb8350b1ca
ms.openlocfilehash: 4c52992071453bc189a3078db9592b02dfb8ba9b
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765324"
---
# <a name="primary-expressions"></a>原始式

基本式は、より複雑な式のビルド ブロックです。 これらは、スコープ解決演算子 () によって修飾されたリテラル、名前、および名前である場合があり `::` ます。 基本式は次のいずれかの形式になります。

*`primary-expression`*\
&emsp;*`literal`*\
&emsp;**`this`**\
&emsp;*`name`*\
&emsp;**`::`** *`name`* **`(`** *`expression`* **`)`**

は *`literal`* 定数のプライマリ式です。 その型は、リテラルの指定の形式によって決まります。 リテラルを指定する方法の詳細については、「 [リテラル](../cpp/numeric-boolean-and-pointer-literals-cpp.md) 」を参照してください。

**`this`** キーワードは、クラスオブジェクトへのポインターです。 非静的メンバー関数内で使用できます。 関数が呼び出されたクラスのインスタンスを指します。 キーワードは、 **`this`** クラスメンバー関数の本体の外側では使用できません。

ポインターの型 **`this`** は、 `type * const` ポインターを `type` 明示的に変更しない関数内の (はクラス名) です **`this`** 。 次の例では、メンバー関数の宣言との型を示し **`this`** ます。

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

ポインターの型を変更する方法の詳細につい **`this`** ては、「 [ `this` ポインター](this-pointer.md)」を参照してください。

スコープ解決演算子 () の **`::`** 後に名前が付いているのは、プライマリ式です。  そのような名前は、メンバー名ではなく、グローバル スコープでの名前であることが必要です。 式の型は、名前の宣言によって決定されます。 宣言名が左辺値の場合は、左辺値 (代入式の左側に表示されることがあります) ですが、 スコープ解決演算子を使用すると、グローバル名が現在のスコープでは隠されていても、その名前を参照できます。 スコープ解決演算子の使用方法の例については、「 [スコープ](../cpp/scope-visual-cpp.md) 」を参照してください。

かっこで囲まれた式は、プライマリ式です。 型と値は、かっこで囲まれていない式の型と値と同じです。 かっこで囲まれていない式が左辺値の場合は左辺値です。

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

これらの例はすべて、次のようなさまざまな形式で、すべての *名前*と見なされます。

```cpp
MyClass // an identifier
MyClass::f // a qualified name
operator = // an operator function name
operator char* // a conversion operator function name
~MyClass // a destructor name
A::B   // a qualified name
A<int> // a template id
```

## <a name="see-also"></a>関連項目

[式の種類](../cpp/types-of-expressions.md)
