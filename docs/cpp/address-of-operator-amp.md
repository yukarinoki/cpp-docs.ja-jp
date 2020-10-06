---
title: 'アドレス演算子: &amp;'
description: C++ 言語のアドレス演算子。
ms.date: 10/02/2020
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: 8ef7ad065281e4de58ddbdebea25950f8eb9dd06
ms.sourcegitcommit: 30792632548d1c71894f9fecbe2f554294b86020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2020
ms.locfileid: "91765281"
---
# <a name="address-of-operator-amp"></a>アドレス演算子: &amp;

## <a name="syntax"></a>構文

> **`&`** *`cast-expression`*

## <a name="remarks"></a>解説

単項アドレス演算子 () は、 **`&`** オペランドのアドレスを受け取ります。 アドレス演算子のオペランドには、関数指定子またはビットフィールドではないオブジェクトを指定する左辺値を指定できます。

アドレス演算子は、ファイルスコープレベルで宣言された基本型、構造体型、クラス型、または共用体型の変数、または添字配列参照にのみ適用できます。 これらの式では、アドレス演算子を含まない定数式を、アドレス式に加算または減算できます。

関数または左辺値に適用されたときの式の結果は、オペランドの型から派生したポインター型 (右辺値) です。 たとえば、オペランドが型の場合、 **`char`** 式の結果はへのポインター型になり **`char`** ます。 またはオブジェクトに適用されるアドレス演算子は、 **`const`** **`volatile`** またはに評価され `const type *` `volatile type *` ます。ここで、 `type` は元のオブジェクトの型です。

オーバーロードされた関数のアドレスは、どのバージョンの関数が参照されているかが明確である場合にのみ取得できます。 特定のオーバーロードされた関数のアドレスを取得する方法については、「 [関数のオーバーロード](function-overloading.md) 」を参照してください。

アドレス演算子が修飾名に適用される場合、結果は、 *修飾名* が静的メンバーを指定しているかどうかによって異なります。 その場合、結果はメンバーの宣言で指定した型へのポインターです。 静的でないメンバーの場合、結果は、*修飾クラス名*で示されるクラスのメンバー*名*へのポインターになります。 *修飾クラス名*の詳細については、「 [Primary 式](../cpp/primary-expressions.md)」を参照してください。

## <a name="example-address-of-static-member"></a>例: 静的メンバーのアドレス

次のコードフラグメントは、クラスメンバーが静的かどうかに応じて、アドレス演算子の結果がどのように異なるかを示しています。

```cpp
// expre_Address_Of_Operator.cpp
// C2440 expected
class PTM {
public:
    int iValue;
    static float fValue;
};

int main() {
   int   PTM::*piValue = &PTM::iValue;  // OK: non-static
   float PTM::*pfValue = &PTM::fValue;  // C2440 error: static
   float *spfValue     = &PTM::fValue;  // OK
}
```

この例では、`&PTM::fValue` 式は、`float *` が静的メンバーであるため、`float PTM::*` 型の代わりに `fValue` を生成します。

## <a name="example-address-of-a-reference-type"></a>例: 参照型のアドレス

参照型にアドレス演算子を適用すると、参照がバインドされたオブジェクトに演算子を適用するのと同じ結果を生成します。 次に例を示します。

```cpp
// expre_Address_Of_Operator2.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main() {
   double d;        // Define an object of type double.
   double& rd = d;  // Define a reference to the object.

   // Obtain and compare their addresses
   if( &d == &rd )
      cout << "&d equals &rd" << endl;
}
```

```Output
&d equals &rd
```

## <a name="example-function-address-as-parameter"></a>例: パラメーターとしての関数アドレス

次の例は、関数へのポインター引数を受け渡すためにアドレス演算子を使用します。

```cpp
// expre_Address_Of_Operator3.cpp
// compile with: /EHsc
// Demonstrate address-of operator &

#include <iostream>
using namespace std;

// Function argument is pointer to type int
int square( int *n ) {
   return (*n) * (*n);
}

int main() {
   int mynum = 5;
   cout << square( &mynum ) << endl;   // pass address of int
}
```

```Output
25
```

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[C++ の組み込み演算子、優先順位、および結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[左辺値参照宣言子: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[間接演算子とアドレス演算子](../c-language/indirection-and-address-of-operators.md)
