---
title: '関係演算子: &lt;、&gt;、&lt;=、および &gt;='
ms.date: 11/04/2016
f1_keywords:
- <
- '>'
helpviewer_keywords:
- '> operator'
- less than operator
- relational operators [C++], syntax
- '>= operator'
- greater than or equal to operators [C++]
- greater than operators [C++]
- < operator
- less than or equal to operator
- <= operator
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
ms.openlocfilehash: 38e05b78d334ca690d9523797f7ca1813834c5d3
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80179121"
---
# <a name="relational-operators-lt-gt-lt-and-gt"></a>関係演算子: &lt;、&gt;、&lt;=、および &gt;=

## <a name="syntax"></a>構文

```
expression < expression
expression > expression
expression <= expression
expression >= expression
```

## <a name="remarks"></a>解説

二項関係演算子は次のリレーションシップを判断します。

- より小さい ( **\<** )

- より大きい ( **>** )

- 以下 ( **\<=** )

- 以上 ( **>=** )

関係演算子の結合規則は、左から右方向です。 関係演算子のオペランドは、両方とも数値型またはポインター型である必要があります。 **Bool**型の値を生成します。 式のリレーションシップが false の場合、返される値は**false** (0) です。それ以外の場合、返される値は**true** (1) です。

## <a name="example"></a>例

```cpp
// expre_Relational_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   cout  << "The true expression 3 > 2 yields: "
         << (3 > 2) << endl
         << "The false expression 20 < 10 yields: "
         << (20 < 10) << endl;
}
```

ストリーム挿入演算子 ( **<<** ) は関係演算子より優先順位が高いため、前の例の式はかっこで囲む必要があります。 したがって、かっこがない最初の式は次のように評価されます。

```cpp
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");
```

[標準変換](standard-conversions.md)で扱う通常の算術変換は、演算型のオペランドに適用されます。

## <a name="comparing-pointers"></a>ポインターの比較

同じ型のオブジェクトへの 2 つのポインターを比較する場合、結果はプログラムのアドレス空間で指すオブジェクトの位置によって決まります。 ポインターは、0または型 `void *`のポインターに評価される定数式と比較することもできます。 ポインターの比較が `void *`型のポインターに対して行われた場合、もう一方のポインターは `void *`型に暗黙的に変換されます。 次に、比較が行われます。

次の場合を除いて、異なる型の 2 つのポインターを比較することはできません。

- 1 つの型が、他の型の派生クラス型である。

- 少なくとも1つのポインターが `void *`型に明示的に変換 (キャスト) されています。 (他のポインターは、変換のために `void *` 型に暗黙的に変換されます)。

同じオブジェクトを指す同じ型の 2 つのポインターは、等しい結果になることが保証されています。 オブジェクトの非静的メンバーへの 2 つのポインターを比較する場合、次の規則が適用されます。

- クラス型が**共用体**ではなく、2つのメンバーが*アクセス指定子*( **public**、 **protected**、 **private**など) で区切られていない場合、last と宣言されたメンバーへのポインターは、前に宣言したメンバーへのポインターよりも大きいものとして比較されます。

- 2つのメンバーが*アクセス指定子*で区切られている場合、結果は未定義になります。

- クラス型が**共用体**の場合、その**共用体**の異なるデータメンバーへのポインターは等しいと見なされます。

2 個のポインターが、同じ配列の要素、または配列の末尾の次の位置の要素をポイントしている場合、より上位の添字を持つオブジェクトへのポインターが高く評価されます。 ポインターの比較は、ポインターが同じ配列のオブジェクトまたは配列の末尾の次の位置を参照している場合にのみ、有効であると保証されます。

## <a name="see-also"></a>参照

[二項演算子を含む式](../cpp/expressions-with-binary-operators.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 関係演算子と等値演算子](../c-language/c-relational-and-equality-operators.md)
