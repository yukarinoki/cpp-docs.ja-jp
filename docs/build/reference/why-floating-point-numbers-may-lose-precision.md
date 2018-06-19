---
title: 浮動小数点数は、有効桁数を失う可能性があります理由 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DBL_EPSILON constant
- FLT_EPSILON constant
- floating-point numbers, precision
ms.assetid: 1acb1add-ac06-4134-a2fd-aff13d8c4c15
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb673f087d98f6c7acdd1e98b5649cc84a48d277
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376138"
---
# <a name="why-floating-point-numbers-may-lose-precision"></a>浮動小数点数の精度の低下
一般に、浮動小数点の 10 進値には正確なバイナリ表現がありません。 これは、CPU が浮動小数点データを表す方法の副作用です。 このため、有効桁数の一部が失われるが発生する可能性があり、浮動小数点演算が予期しない結果を生成可能性があります。  
  
 この動作は、次のいずれかの結果を示します。  
  
-   10 進数のバイナリ表現を正確なことができない可能性があります。  
  
-   使用する数値 (float や double のミキシングなど) の間で型の不一致があります。  
  
 動作を解決するには、取得する値が大きいか小さいものとは、必要なほとんどのプログラマ、またはこれらと精度を維持するための Binary Coded Decimal (BCD) ライブラリを使用します。  
  
 浮動小数点値のバイナリ表現では、有効桁数と浮動小数点演算の精度に影響します。 Microsoft Visual C を使用して[IEEE 浮動小数点形式](../../build/reference/ieee-floating-point-representation.md)です。  
  
## <a name="example"></a>例  
  
```  
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
 EPSILON、1.192092896e として float に対して定義されている FLT_EPSILON 定数を使用できます-07F、または倍精度 2.2204460492503131e として定義されている DBL_EPSILON-016 です。 これらの定数の float.h を含める必要があります。 これらの定数が定義されている最も小さい正の値として x 番号は、このような x + 1.0 は 1.0 に等しくします。 これは非常に小さい数であるため、非常に大きな数値に関連する計算のユーザー定義許容値を使用する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [コードの最適化](../../build/reference/optimizing-your-code.md)