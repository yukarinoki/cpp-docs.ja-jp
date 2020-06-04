---
title: 'コンマ演算子: ,'
ms.date: 11/04/2016
f1_keywords:
- '%2C'
helpviewer_keywords:
- comma operator
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
ms.openlocfilehash: 6ea2bd5c0e7653ba7f81531a5c39df2da41662a9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189768"
---
# <a name="comma-operator-"></a>コンマ演算子: ,

1 つのステートメントが期待される場所で 2 つのステートメントをグループ化します。

## <a name="syntax"></a>構文

```
expression , expression
```

## <a name="remarks"></a>解説

コンマ演算子の結合規則は、左から右方向です。 コンマで区切られた 2 つの式は左から右に評価されます。 左オペランドは常に評価され、右オペランドが評価される前にすべての副作用が完了します。

コンマは、関数の引数リストなどの一部のコンテキストで、区切り記号として使用できます。 区切り記号としてのコンマの使用と演算子としての使用を混同しないでください。この 2 つの用途は、まったく別のものです。

式 `e1, e2` を考えます。 式の型と値は、 *e2*の型と値です。*e1*を評価した結果は破棄されます。 結果は、右オペランドが左辺値の場合は左辺値です。

通常、コンマが区切り記号として使用される場所 (たとえば、関数の実引数や集約の初期化子) では、コンマ演算子とそのオペランドをかっこで囲む必要があります。 次に例を示します。

```cpp
func_one( x, y + 2, z );
func_two( (x--, y + 2), z );
```

前の `func_one` の関数呼び出しでは、`x`、`y + 2`、`z` という 3 つの引数がコンマで区切られて渡されます。 `func_two` の関数呼び出しでは、かっこにより、コンパイラは順次評価演算子として最初のコンマを解釈します。 この関数呼び出しは、`func_two` に 2 つの引数を渡します。 最初の引数は、順次評価演算 `(x--, y + 2)` の結果です。この演算は、式 `y + 2` の値と型を持ち、第 2 の引数は `z` です。

## <a name="example"></a>例

```cpp
// cpp_comma_operator.cpp
#include <stdio.h>
int main () {
   int i = 10, b = 20, c= 30;
   i = b, c;
   printf("%i\n", i);

   i = (b, c);
   printf("%i\n", i);
}
```

```Output
20
30
```

## <a name="see-also"></a>参照

[二項演算子を含む式](../cpp/expressions-with-binary-operators.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[順次評価演算子](../c-language/sequential-evaluation-operator.md)
