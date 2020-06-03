---
title: '1&#39;s 補数演算子: ~'
ms.date: 11/04/2016
f1_keywords:
- "~"
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: 777f253925caf38647863bdaa93fde8d5a03e3f9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177717"
---
# <a name="one39s-complement-operator-"></a>1&#39;s 補数演算子: ~

## <a name="syntax"></a>構文

```
~ cast-expression
```

## <a name="remarks"></a>解説

1 の補数演算子 (`~`) は、"ビット補数" 演算子とも呼ばれ、オペランドのビットごとの 1 の補数を生成します。 つまり、オペランドの各ビットが 1 である場合の結果は、0 になります。 逆に、オペランドの各ビットが 0 である場合の結果は、1 になります。 1 の補数演算子のオペランドは、整数型である必要があります。

## <a name="operator-keyword-for-"></a>~ の演算子キーワード

**Compl**演算子は `~`に相当するテキストです。 プログラムの**compl**演算子にアクセスするには、ヘッダーファイル `iso646.h`を含める方法と、 [/za](../build/reference/za-ze-disable-language-extensions.md)を指定してコンパイルする方法の2つの方法があります。

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

整数の上位変換は、整数オペランドに対して実行され、結果の型は、そのオペランドが昇格される型になります。 プロモーションの実行方法の詳細については、「[標準変換](standard-conversions.md)」を参照してください。

## <a name="see-also"></a>参照

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[単項算術演算子](../c-language/unary-arithmetic-operators.md)
