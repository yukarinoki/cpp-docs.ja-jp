---
title: '等値演算子: == および !='
ms.date: 11/04/2016
f1_keywords:
- '!='
- ==
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
ms.openlocfilehash: 7e42b66438579bc9be6274863366762b8b4ffbe9
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444402"
---
# <a name="equality-operators--and-"></a>等値演算子: == および !=

## <a name="syntax"></a>構文

```
expression == expression
expression != expression
```

## <a name="remarks"></a>コメント

これらの二項等値演算子はそれぞれオペランドを比較し、等しいか、等しくないかを判別します。

"等しい" (`==`) および "等しくない" (`!=`) の等値演算子は関係演算子より優先順位が下ですが、動作は同じです。 これらの演算子の結果型は**bool**です。

Equal to 演算子 (`==`) では、両方のオペランドの値が同じである場合、 **true** (1) が返されます。それ以外の場合は**false** (0) を返します。 不等号演算子 (`!=`) は、オペランドの値が同じでない場合に**true**を返します。それ以外の場合は**false**を返します。

## <a name="operator-keyword-for-"></a>!= の演算子キーワード

`not_eq` 演算子は `!=` の代替表現です。 プログラム内の `not_eq` 演算子にアクセスするには、ヘッダーファイル `iso646.h`を含める方法と、 [/za](../build/reference/za-ze-disable-language-extensions.md) (言語拡張機能の無効化) コンパイラオプションを使用してコンパイルする方法の2つの方法があります。

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

## <a name="see-also"></a>参照

[二項演算子を含む式](../cpp/expressions-with-binary-operators.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 関係演算子と等値演算子](../c-language/c-relational-and-equality-operators.md)