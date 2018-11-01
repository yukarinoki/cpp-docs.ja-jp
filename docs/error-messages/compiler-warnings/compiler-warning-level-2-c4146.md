---
title: コンパイラの警告 (レベル 2) C4146
ms.date: 11/04/2016
f1_keywords:
- C4146
helpviewer_keywords:
- C4146
ms.assetid: d6c31ab1-3120-40d5-8d80-32b5f7046e32
ms.openlocfilehash: 8b3090f1bc3a64752ede4dab2b1e1b5cd800057d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555572"
---
# <a name="compiler-warning-level-2-c4146"></a>コンパイラの警告 (レベル 2) C4146

単項マイナス演算子の結果はまだ署名されていない符号なしの型に適用します。

符号なしの型は、単項マイナス (否定) は、通常は無意味符号なしの型に適用すると、のみ非負の値を保持できます。 オペランドと結果の両方は、負でないです。

実際には、これは、プログラマが最小の整数の値は-2147483648 を express しようとするときに発生します。 式が 2 つのステージで処理されるため、この値は-2147483648 として記述することはできません。

1. 2147483648 数が評価されます。 2147483648 の型でない 2147483647 の整数値の最大値よりも大きいため、 [int](../../c-language/integer-types.md)が`unsigned int`します。

1. 単項マイナスは 2147483648 に符号なしの結果で、値に適用されます。

結果の符号なしの型には、予期しない動作を可能性があります。 比較では、結果が使用されるかどうかは、符号なしの比較される可能性があります、たとえば、もう一方のオペランドが、`int`します。 これは、次のサンプル プログラムが 1 つの行を出力する理由について説明します。

必要な 2 行目で、 `1 is greater than the most negative int`、ためには印刷されません`((unsigned int)1) > 2147483648`は false です。

型を持つ、limits.h から INT_MIN を使用して、C4146 を回避できます**int を署名**します。

## <a name="example"></a>例

次の例では、C4146 が生成されます。

```
// C4146.cpp
// compile with: /W2
#include <stdio.h>

void check(int i)
{
    if (i > -2147483648)   // C4146
        printf_s("%d is greater than the most negative int\n", i);
}

int main()
{
    check(-100);
    check(1);
}
```