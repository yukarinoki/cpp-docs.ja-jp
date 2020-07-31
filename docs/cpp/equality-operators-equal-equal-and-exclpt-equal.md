---
title: '等値演算子: == および !='
description: C++ 標準言語の等価演算子と非等値演算子の構文で、を使用します。
ms.date: 07/23/2020
f1_keywords:
- '!='
- ==
- not_eq_cpp
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
ms.openlocfilehash: 567b83e99dce0354626f08a4788f1343314493b1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227544"
---
# <a name="equality-operators--and-"></a>等値演算子: == および !=

## <a name="syntax"></a>構文

> *式* **`==`***式*\
> *式* **`!=`***式*

## <a name="remarks"></a>解説

これらの二項等値演算子はそれぞれオペランドを比較し、等しいか、等しくないかを判別します。

等値演算子 ( **`==`** ) と等しくない () は、 **`!=`** 関係演算子より優先順位が低くなりますが、同じように動作します。 これらの演算子の結果の型は **`bool`** です。

Equal to 演算子 () は、 **`==`** **`true`** 両方のオペランドの値が同じである場合はを返します。それ以外の場合はを返し **`false`** ます。 不等号演算子 () は、 **`!=`** **`true`** オペランドの値が同じでない場合はを返します。それ以外の場合はを返し **`false`** ます。

## <a name="operator-keyword-for-"></a>! = の Operator キーワード

C++ **`not_eq`** では、の代替スペルとしてを指定し **`!=`** ます。 (の別のスペルはありません **`==`** )。C では、代替のスペルは、ヘッダーにマクロとして指定され \<iso646.h> ます。 C++ では、代替のスペルはキーワードです。\<iso646.h>または C++ と同等のの使用 \<ciso646> は非推奨とされます。 Microsoft C++ では、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) またはコンパイラオプションを使用して、 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 別のスペルチェックを有効にする必要があります。

## <a name="example"></a>例

```cpp
// expre_Equality_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   cout  << boolalpha
         << "The true expression 3 != 2 yields: "
         << (3 != 2) << endl
         << "The false expression 20 == 10 yields: "
         << (20 == 10) << endl;
}
```

等値演算子は、同じ型のメンバーへのポインターを比較できます。 このような比較では、ポインターからメンバーへの変換が実行されます。 メンバーへのポインターは、0 として評価される定数式と比較することもできます。

## <a name="see-also"></a>関連項目

[二項演算子を含む式](../cpp/expressions-with-binary-operators.md)<br/>
[C++ の組み込み演算子、優先順位、結合規則と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C の関係演算子と等値演算子](../c-language/c-relational-and-equality-operators.md)
