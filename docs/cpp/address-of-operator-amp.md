---
title: 'アドレス演算子: &amp;'
ms.date: 11/04/2016
f1_keywords:
- '&'
helpviewer_keywords:
- address-of operator (&)
- '& operator'
- '& operator [C++], address-of operator'
ms.assetid: 2828221a-15f6-4acc-87fe-25e34feebb88
ms.openlocfilehash: 4c9ae9aedaec202c8798ab454ee5df1a68278a6d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181604"
---
# <a name="address-of-operator-amp"></a>アドレス演算子: &amp;

## <a name="syntax"></a>構文

```
& cast-expression
```

## <a name="remarks"></a>解説

単項アドレス演算子 ( **&** ) は、オペランドのアドレスを受け取ります。 アドレス演算子のオペランドには、関数指定子またはビットフィールドではないオブジェクトを指定する左辺値のいずれかを指定できます。

アドレス演算子は、ファイル スコープ レベルで宣言された基本型、構造体型、クラス型、または共用体型を持つ変数、または添字配列参照だけに適用できます。 これらの式では、アドレス演算子を含まない定数式を、アドレス式に加算したりアドレス式から減算できます。

関数または左辺値に適用されたときの式の結果は、オペランドの型から派生したポインター型 (右辺値) です。 たとえば、オペランドが**char**型の場合、式の結果は**char**へのポインター型になります。 **Const**または**volatile**オブジェクトに適用されるアドレス演算子は、`const type *` または `volatile type *`に評価されます。ここで、 **type**は元のオブジェクトの型です。

アドレス演算子が修飾名に適用される場合、結果は、*修飾名*が静的メンバーを指定しているかどうかによって異なります。 その場合、結果はメンバーの宣言で指定した型へのポインターです。 メンバーが静的でない場合、結果は、*修飾クラス名*で示されるクラスのメンバー*名*へのポインターになります。 (*修飾クラス名*の詳細については、「[主な式](../cpp/primary-expressions.md)」を参照してください)。次のコードフラグメントは、メンバーが静的かどうかに応じて、結果がどのように異なるかを示しています。

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

オーバーロード関数のアドレスは、どのバージョンの関数が参照されているかが明らかな場合にのみ受け取ることができます。 特定のオーバーロードされた関数のアドレスを取得する方法については、「[関数のオーバーロード](function-overloading.md)」を参照してください。

参照型にアドレス演算子を適用すると、参照がバインドされたオブジェクトに演算子を適用するのと同じ結果を生成します。 次に例を示します。

## <a name="example"></a>例

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

## <a name="output"></a>Output

```Output
&d equals &rd
```

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

## <a name="output"></a>Output

```Output
25
```

## <a name="see-also"></a>参照

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[左辺値参照宣言子: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[間接演算子とアドレス演算子](../c-language/indirection-and-address-of-operators.md)
