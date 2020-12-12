---
description: 詳細については、「乗算演算子と剰余演算子」を参照してください。
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
ms.openlocfilehash: e3e3e3823abb255922bf31be90b4a116fb100efe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313867"
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

- 乗算 ( <strong>\*</strong> )

- 除算 ( **/** )

- 剰余 (除算の剰余) ( **%** )

これらの二項演算子の結合規則は、左から右方向です。

乗算演算子は、数値型のオペランドを受け取ります。 剰余演算子 () には、 **%** オペランドが整数型である必要があるという、より厳しい要件があります。 (浮動小数点除算の剰余を取得するには、ランタイム関数 [fmod](../c-runtime-library/reference/fmod-fmodf.md)を使用します)。「 [標準変換](standard-conversions.md) 」で説明されている変換がオペランドに適用され、結果は変換後の型になります。

乗算演算子は、最初のオペランドを 2 番目のオペランドで乗算した結果を生成します。

除算演算子は、最初のオペランドを 2 番目のオペランドで除算した結果を生成します。

剰余演算子は、次の式によって指定された剰余を生成し *ます。ここ* で、 *e1* は最初のオペランド、 *e2* は2番目の *オペランド (e1*  /  *e2*) \* *e2*、両方のオペランドが整数型であることを示します。

除算または剰余式における 0 での除算は未定義になり、実行時エラーが発生します。 したがって、次の式は未定義の間違った結果を生成します。

```cpp
i % 0
f / 0.0
```

乗算式、除算式、剰余式への両方のオペランドに同じ符号がある場合、結果は正の値になります。 それ以外の場合、結果は負になります。 剰余演算の符号の結果は実装定義されます。

> [!NOTE]
> 乗算演算子によって実行される変換ではオーバーフロー条件やアンダーフロー条件が提供されないため、乗算演算の結果を変換後のオペランドの型で表すことができない場合、情報が失われる可能性があります。

**Microsoft 固有の仕様**

Microsoft C++ では、剰余式の結果は常に最初のオペランドと同じ符号になります。

**Microsoft 固有の仕様はここまで**

2 つの整数の計算された除算が正確ではなく、1 つのオペランドだけが負の値の場合、結果は、除算演算で算出された正確な値未満の最大の整数 (大きさでは、符号を無視します) になります。 たとえば、-11/3 の計算値は-3.666666666 です。 その整数部の結果は-3 になります。

乗算演算子間のリレーションシップは、id (*e1*  /  *e2*) \* *e2*  +  *e1*  %  *e2*  ==  *e1* によって指定されます。

## <a name="example"></a>例

次のプログラムは乗算演算子を示します。 のいずれかのオペランド `10 / 3` は、切り捨てを避けるために明示的に型にキャストする必要があり **`float`** ます。これにより、両方のオペランドが除算前の型になり **`float`** ます。

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
