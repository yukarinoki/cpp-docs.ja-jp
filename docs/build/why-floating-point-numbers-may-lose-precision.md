---
title: 浮動小数点数の精度の低下
ms.date: 11/04/2016
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
ms.openlocfilehash: 373ce9fa2c2c96fac349940076873a4a637a9dbe
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298715"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>浮動小数点数の精度の低下

通常、浮動小数点数には、正確なバイナリ表現がありません。 これは、CPU で浮動小数点データを表す方法の副作用です。 このため、精度が低下したり、一部の浮動小数点演算で予期しない結果が生じる場合があります。

この動作は、次のいずれかの結果になります。

- 10 進数のバイナリ表現が正確でない場合があります。

- 使用される数値間に型の不一致があります (たとえば、float と double の混在)。

この動作を解決するために、ほとんどのプログラマは、値が必要な値よりも大きいまたは小さいことを確認するか、精度が維持される 2 進化 10 進数 (BCD) ライブラリを取得して使用します。

浮動小数点値のバイナリ表現は、浮動小数点演算の精度と正確性に影響します。 Microsoft Visual C++ では、[IEEE 浮動小数点形式](ieee-floating-point-representation.md)が使用されています。

## <a name="example"></a>例

```c
// Floating-point_number_precision.c
// Compile options needed: none. Value of c is printed with a decimal
// point precision of 10 and 6 (printf rounded value by default) to
// show the difference
#include <stdio.h>

#define EPSILON 0.0001   // Define your own tolerance
#define FLOAT_EQ(x,v) (((v - EPSILON) < x) && (x <( v + EPSILON)))

int main() {
   float a, b, c;

   a = 1.345f;
   b = 1.123f;
   c = a + b;
   // if (FLOAT_EQ(c, 2.468)) // Remove comment for correct result
   if (c == 2.468)            // Comment this line for correct result
      printf_s("They are equal.\n");
   else
      printf_s("They are not equal! The value of c is %13.10f "
                "or %f",c,c);
}
```

```Output
They are not equal! The value of c is  2.4679999352 or 2.468000
```

## <a name="comments"></a>コメント

EPSILON の場合、float に対して 1.192092896e-07F と定義される定数 FLT_EPSILON、または double に対して 2.2204460492503131e-016 と定義される DBL_EPSILON を使用できます。 これらの定数のために float.h を含める必要があります。 これらの定数は、x + 1.0 が 1.0 と等しくない最小の正の数 x と定義されます。 これは非常に小さい数値であるため、非常に大きい数値を含む計算にはユーザー定義の許容範囲を使用する必要があります。

## <a name="see-also"></a>関連項目

[コードの最適化](optimizing-your-code.md)
