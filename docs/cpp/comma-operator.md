---
title: 'コンマ演算子: |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '%2C'
dev_langs:
- C++
helpviewer_keywords:
- comma operator
ms.assetid: 38e0238e-19da-42ba-ae62-277bfdab6090
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d9beadf4f532d24ca1f4023ad95dd8583d653c11
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707769"
---
# <a name="comma-operator-"></a>コンマ演算子: ,
1 つのステートメントが期待される場所で 2 つのステートメントをグループ化します。  
  
## <a name="syntax"></a>構文  
  
```  
expression , expression  
```  
  
## <a name="remarks"></a>Remarks  
 コンマ演算子の結合規則は、左から右方向です。 コンマで区切られた 2 つの式は左から右に評価されます。 左オペランドは常に評価され、右オペランドが評価される前にすべての副作用が完了します。  
  
 コンマは、関数の引数リストなどの一部のコンテキストで、区切り記号として使用できます。 区切り記号としてのコンマの使用と演算子としての使用を混同しないでください。この 2 つの用途は、まったく別のものです。  
  
 式 `e1, e2` を考えます。 型と式の値は型と値の*e2*; の評価結果*e1*は破棄されます。 結果は、右オペランドが左辺値の場合は左辺値です。  
  
 通常、コンマが区切り記号として使用される場所 (たとえば、関数の実引数や集約の初期化子) では、コンマ演算子とそのオペランドをかっこで囲む必要があります。 例えば:  
  
```cpp 
func_one( x, y + 2, z );  
func_two( (x--, y + 2), z );  
```  
  
 前の `func_one` の関数呼び出しでは、`x`、`y + 2`、`z` という 3 つの引数がコンマで区切られて渡されます。 `func_two` の関数呼び出しでは、かっこにより、コンパイラは順次評価演算子として最初のコンマを解釈します。 この関数呼び出しは、`func_two` に 2 つの引数を渡します。 最初の引数は、順次評価演算 `(x--, y + 2)` の結果です。この演算は、式 `y + 2` の値と型を持ち、第 2 の引数は `z` です。  
  
## <a name="example"></a>例  
  
```cpp 
// cpp_comma_operator.cpp  
#include <stdio.h>  
int main () {  
   int i = 10, b = 20, c= 30;  
   i = b, c;  
   printf("%i\n", i);  
  
   i = (b, c);  
   printf("%i\n", i);  
}  
```  
  
```Output  
20  
30  
```  
  
## <a name="see-also"></a>関連項目  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [順次評価演算子](../c-language/sequential-evaluation-operator.md)