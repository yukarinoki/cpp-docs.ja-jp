---
title: C 浮動小数点定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- types [C], constants
- floating-point numbers, floating-point constants
- constants, floating-point
- floating-point constants
- floating-point constants, about floating-point constants
- double data type, floating-point constants
ms.assetid: e1bd9b44-d6ab-470c-93e5-07142c7a2062
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3608e40db2aa3eb0c49942de278c1d428e26689f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="c-floating-point-constants"></a>C 浮動小数点定数
"浮動小数点定数" は符号付き実数を表す 10 進数です。 符号付き実数の表現には、整数部分、小数部分、および指数が含まれます。 変更できない浮動小数点値を表すには、浮動小数点定数を使用します。  
  
## <a name="syntax"></a>構文  
 *floating-point-constant*:  
 &nbsp;&nbsp; *fractional-constant exponent-part*<sub>opt</sub> *floating-suffix*<sub>opt</sub>  
 &nbsp;&nbsp; *digit-sequence exponent-part floating-suffix*<sub>opt</sub>  
  
 *fractional-constant*:  
 &nbsp;&nbsp; *digit-sequence*<sub>opt</sub> **.** *digit-sequence*  
 &nbsp;&nbsp; *digit-sequence*  **.**  
  
 *exponent-part*:  
 &nbsp;&nbsp; **e**  *sign*<sub>opt</sub> *digit-sequence*  
 &nbsp;&nbsp; **E**  *sign*<sub>opt</sub> *digit-sequence*  
  
 *sign* : 次のいずれか  
 &nbsp;&nbsp; **+ -**  
  
 *digit-sequence*:  
 &nbsp;&nbsp; *digit*  
 &nbsp;&nbsp; *digit-sequence digit*  
  
 *floating-suffix*: 次のいずれか  
 &nbsp;&nbsp; **f l F L**  
  
 小数点の前の桁 (値の整数の部分) または小数点の後の桁 (小数の部分) を省略できますが、両方を省略することはできません。 指数を含めた場合にのみ、小数点を省略することができます。 空白文字で定数の数値または文字を分離することはできません。  
  
 次の例では、浮動小数点定数と式のフォームをいくつか示します。  
  
```  
15.75  
1.575E1   /* = 15.75   */  
1575e-2   /* = 15.75   */  
-2.5e-3   /* = -0.0025 */  
25E-4     /* =  0.0025 */  
```  
  
 浮動小数点定数は、負符号 (**-**) が前にない限り、正の値です。 この場合、負符号は単項算術否定演算子として扱われます。 浮動小数点定数には、`float`、`double`、または `long double` 型があります。  
  
 **f**、**F**、**l**、または **L** のサフィックスのない浮動小数点定数は、`double` 型を持ちます。 文字 **f** または **F** がサフィックスの場合、定数の型は `float` になります。 末尾に文字 **l** また **L** が付いている場合、`long double` 型になります。 例:  
  
```  
100L  /* Has type long double  */  
100F  /* Has type float        */  
```  
  
 Microsoft C コンパイラは、`double` 型と同じように内部的に `long double` を表すことに注意してください。 `double`、`float`、および `long double` 型については、「[基本型の格納](../c-language/storage-of-basic-types.md)」を参照してください。  
  
 次の例に示すように、浮動小数点定数の整数の部分を省略できます。 数値 .75 は、次のようなさまざまな方法で表現されます。  
  
```  
.0075e2  
0.075e1  
.075e1  
75e-2  
```  
  
## <a name="see-also"></a>参照  
 [C 定数](../c-language/c-constants.md)