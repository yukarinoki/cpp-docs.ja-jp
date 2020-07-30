---
title: '1 の補数演算子: ~'
description: C++ 標準言語1の補数演算子構文で、を使用します。
ms.date: 07/23/2020
f1_keywords:
- "~"
- compl_cpp
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: 89c67855cd67df2af315cea941b487e7462889b2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227245"
---
# <a name="ones-complement-operator-"></a>1 の補数演算子: ~

## <a name="syntax"></a>構文

```cpp
~ cast-expression
```

## <a name="remarks"></a>解説

1の補数演算子 () は、 **`~`** *ビットごとの補数*演算子とも呼ばれ、オペランドのビットごとの1の補数を生成します。 つまり、オペランドの各ビットが 1 である場合の結果は、0 になります。 逆に、オペランドの各ビットが 0 である場合の結果は、1 になります。 1 の補数演算子のオペランドは、整数型である必要があります。

## <a name="operator-keyword-for-"></a>~ の Operator キーワード

C++ **`compl`** では、の代替スペルとしてを指定し **`~`** ます。 C では、代替のスペルは、ヘッダーにマクロとして指定され \<iso646.h> ます。 C++ では、代替のスペルはキーワードです。\<iso646.h>または C++ と同等のの使用 \<ciso646> は非推奨とされます。 Microsoft C++ では、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) またはコンパイラオプションを使用して、 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 別のスペルチェックを有効にする必要があります。

## <a name="example"></a>例

```cpp
// expre_One_Complement_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main () {
   unsigned short y = 0xFFFF;
   cout << hex << y << endl;
   y = ~y;   // Take one's complement
   cout << hex << y << endl;
}
```

この例では、`y` に割り当てられた新しい値は、符号なしの値 0xFFFF の 1 の補数、つまり 0x0000 です。

整数の上位変換が整数オペランドに対して実行されます。 オペランドが昇格される型は、結果の型です。 整数の上位変換の詳細については、「[標準変換](standard-conversions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[単項演算子を含む式](expressions-with-unary-operators.md)<br/>
[C++ の組み込み演算子、優先順位、および結合規則](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[単項算術演算子](../c-language/unary-arithmetic-operators.md)
