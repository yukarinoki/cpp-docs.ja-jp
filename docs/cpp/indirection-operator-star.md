---
title: '間接演算子: *'
ms.date: 11/04/2016
helpviewer_keywords:
- '* operator'
- indirection operator
- operators [C++], indirection
- indirection operator [C++], syntax
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
ms.openlocfilehash: 8f27cfd943455d52b04c41ef2d2d83e6e03a84c0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80178280"
---
# <a name="indirection-operator-"></a>間接演算子: *

## <a name="syntax"></a>構文

```
* cast-expression
```

## <a name="remarks"></a>解説

単項間接演算子 (<strong>\*</strong>) は、ポインターを逆参照します。つまり、ポインター値を左辺値に変換します。 間接演算子のオペランドを型へのポインターにすることはできません。 間接式の結果は、ポインター型の派生元の型です。 このコンテキストでの<strong>\*</strong>演算子の使用は、乗算である二項演算子とは異なります。

オペランドが関数を指している場合、結果は関数指定子になります。 格納場所を指している場合、結果は格納場所を指定する左辺値になります。

間接演算子は、ポインターへのポインターを逆参照するために累積的に使用される場合があります。 次に例を示します。

```cpp
// expre_Indirection_Operator.cpp
// compile with: /EHsc
// Demonstrate indirection operator
#include <iostream>
using namespace std;
int main() {
   int n = 5;
   int *pn = &n;
   int **ppn = &pn;

   cout  << "Value of n:\n"
         << "direct value: " << n << endl
         << "indirect value: " << *pn << endl
         << "doubly indirect value: " << **ppn << endl
         << "address of n: " << pn << endl
         << "address of n via indirection: " << *ppn << endl;
}
```

ポインターの値が無効な場合、結果は未定義になります。 次の一覧に、ポインター値が無効になる一般的な条件をいくつか示します。

- ポインターが null ポインターです。

- ポインターが、参照時に見えないローカル項目のアドレスを指定しています。

- ポインターが、指されているオブジェクトの型ではアラインメントが不適切なアドレスを指定しています。

- ポインターが、実行プログラムで使用されていないアドレスを指定しています。

## <a name="see-also"></a>参照

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[address-of 演算子: &](../cpp/address-of-operator-amp.md)<br/>
[間接演算子とアドレス演算子](../c-language/indirection-and-address-of-operators.md)
