---
title: 乗算演算子と剰余演算子
ms.date: 11/04/2016
f1_keywords:
- '%'
- /
helpviewer_keywords:
- operators [C++], multiplicative
- arithmetic operators [C++], multiplicative operators
- modulus operator [C++]
- '* operator'
- division operator [C++], multiplicative operators
- '% operator'
- multiplication operator [C++], multiplicative operators
- multiplicative operators [C++]
- division operator
ms.assetid: b53ea5da-d0b4-40dc-98f3-0aa52d548293
ms.openlocfilehash: 791f18793b49f7d3a986c3271fddef3acef33062
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367924"
---
# <a name="multiplicative-operators-and-the-modulus-operator"></a>乗算演算子と剰余演算子

## <a name="syntax"></a>構文

```
expression * expression
expression / expression
expression % expression
```

## <a name="remarks"></a>解説

乗算演算子は次のとおりです。

- 乗算 (<strong>\*</strong>)

- ディビジョン**/**( )

- モジュラス (除算からの剰**%** 余) ( )

これらの二項演算子の結合規則は、左から右方向です。

乗算演算子は、数値型のオペランドを受け取ります。 剰余演算子 (**%**) は、オペランドが整数型でなければならないというより厳密な要件を持っています。 (浮動小数点除算の残りの部分を取得するには、実行時関数[fmod](../c-runtime-library/reference/fmod-fmodf.md)を使用します。[標準変換](standard-conversions.md)で扱う変換はオペランドに適用され、結果は変換された型になります。

乗算演算子は、最初のオペランドを 2 番目のオペランドで乗算した結果を生成します。

除算演算子は、最初のオペランドを 2 番目のオペランドで除算した結果を生成します。

剰余演算子は、次の式で指定された剰余を生成しますが *、e1*は最初のオペランドで *、e2*は*e1* / *e2*2 番目のオペランド\**e2**です。*

除算または剰余式における 0 での除算は未定義になり、実行時エラーが発生します。 したがって、次の式は未定義の間違った結果を生成します。

```cpp
i % 0
f / 0.0
```

乗算式、除算式、剰余式への両方のオペランドに同じ符号がある場合、結果は正の値になります。 それ以外の場合、結果は負になります。 剰余演算の符号の結果は実装定義されます。

> [!NOTE]
> 乗算演算子によって実行される変換ではオーバーフロー条件やアンダーフロー条件が提供されないため、乗算演算の結果を変換後のオペランドの型で表すことができない場合、情報が失われる可能性があります。

**マイクロソフト固有**

Microsoft C++ では、剰余式の結果は常に最初のオペランドと同じ符号になります。

**エンド マイクロソフト 固有**

2 つの整数の計算された除算が正確ではなく、1 つのオペランドだけが負の値の場合、結果は、除算演算で算出された正確な値未満の最大の整数 (大きさでは、符号を無視します) になります。 たとえば、-11/3 の計算値は -3.66666666 です。 その積分分割の結果は-3です。

乗算演算子間の関係は、ID (*e1* / *e2* \* ) *e2 e2* + *e2* == *e1**e1* % によって与えられます。

## <a name="example"></a>例

次のプログラムは乗算演算子を示します。 両方の`10 / 3`オペランドが除算**の前に** **float**型になるように、いずれかのオペランドを float 型に明示的にキャストして、切り捨てを避ける必要があることに注意してください。

```cpp
// expre_Multiplicative_Operators.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main() {
   int x = 3, y = 6, z = 10;
   cout  << "3 * 6 is " << x * y << endl
         << "6 / 3 is " << y / x << endl
         << "10 % 3 is " << z % x << endl
         << "10 / 3 is " << (float) z / x << endl;
}
```

## <a name="see-also"></a>関連項目

[二項演算子を含む式](../cpp/expressions-with-binary-operators.md)<br/>
[C++ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 乗算演算子](../c-language/c-multiplicative-operators.md)
