---
title: C 乗算演算子 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arithmetic operators [C++], multiplicative operators
- / operator
- / operator, multiplicative operators
- remainder operator (%)
- operators [C], multiplication
- '% operator'
- slash (/) operator
- multiplication operator [C++], multiplicative operators
ms.assetid: 495471c9-319b-4eb4-bd97-039a025fd3a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1810cc9dd7a991e302e0e9e2db69f65aebebc613
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="c-multiplicative-operators"></a>C 乗算演算子
乗算演算子は、乗算 (**\***)、除算 (**/**)、および剰余 (`%`) 演算を実行します。  
  
 **構文**  
  
 *multiplicative-expression*:  
 *cast-expression*  
  
 *multiplicative-expression*  **\***  *cast-expression*  
  
 *multiplicative-expression*  **/**  *cast-expression*  
  
 *multiplicative-expression*  **%**  *cast-expression*  
  
 剰余演算子 (`%`) のオペランドは整数である必要があります。 乗算 (**\***) 演算子と除算 (**/**) 演算子は、整数型または浮動小数点型のオペランドを取ることができます。オペランドの型が違ってもかまいません。  
  
 乗算演算子は、オペランドに通常の算術変換を実行します。 結果の型は、変換後のオペランドの型です。  
  
> [!NOTE]
>  乗算演算子によって実行される変換ではオーバーフロー条件やアンダーフロー条件が提供されないため、乗算演算の結果を変換後のオペランドの型で表すことができない場合、情報が失われる可能性があります。  
  
 C の乗算演算子について、以下に説明します。  
  
|演算子|説明|  
|--------------|-----------------|  
|**\***|乗算演算子は 2 つのオペランドを乗算します。|  
|**/**|除算演算子は、最初のオペランドを 2 番目のオペランドで除算します。 2 つの整数オペランドで除算が行われ、結果が整数でない場合、結果は次の規則に従って切り捨てられます。|  
||0 による除算の結果は、ANSI C 規格に従って未定義になります。 Microsoft C コンパイラは、コンパイル時または実行時にエラーを生成します。|  
||-   両方のオペランドが正の値または符号なしである場合、結果は 0 方向に切り捨てられます。|  
||-   どちらかのオペランドが負の値の場合、演算の結果が代数的な商以下の最大の整数になるか代数的な商以上の最小の整数になるかは、実装定義になります。 (以下の「Microsoft 固有の仕様」セクションを参照してください)。|  
|`%`|剰余演算子の結果は、最初のオペランドを 2 番目のオペランドで除算したときの剰余です。 除算が厳密にできない場合、結果は次の規則によって決定されます。|  
||-   右のオペランドがゼロの場合、結果は未定義になります。|  
||-   両方のオペランドが正の値または符号なしである場合、結果は正の値になります。|  
||-   どちらかのオペランドが負の値で、結果が厳密でない場合、結果は実装定義になります。 (以下の「Microsoft 固有の仕様」セクションを参照してください)。|  
  
 **Microsoft 固有の仕様**  
  
 いずれかのオペランドが負である除算では、切り捨ての方向は 0 方向になります。  
  
 剰余演算子による除算で、いずれかのオペランドが負の値である場合、結果は被除数 (式の 1 つ目のオペランド) と同じ符号を持ちます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="examples"></a>使用例  
 次に示す宣言は、その後の例で使用されます。  
  
```  
int i = 10, j = 3, n;  
double x = 2.0, y;  
```  
  
 次のステートメントでは、乗算演算子を使用しています。  
  
```  
y = x * i;  
```  
  
 この場合は、`x` が `i` で乗算されて、値 20.0 が返されます。 結果は **double** 型になります。  
  
```  
n = i / j;  
```  
  
 この例では、10 が 3 で除算されています。 結果は 0 方向に切り捨てられ、整数値 3 が生成されます。  
  
```  
n = i % j;  
```  
  
 このステートメントでは、10 を 3 で除算したときの剰余である整数 1 が `n` に代入されます。  
  
 **Microsoft 固有の仕様**  
  
 剰余の符号は、被除数の符号と同じです。 例:  
  
```  
50 % -6 = 2  
-50 % 6 = -2  
```  
  
 どちらの場合も、`50` と `2` の符号が同じになっています。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [乗算演算子と剰余演算子](../cpp/multiplicative-operators-and-the-modulus-operator.md)