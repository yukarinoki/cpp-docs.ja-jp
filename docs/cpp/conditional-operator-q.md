---
title: '条件演算子: しますか? : |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '?:'
- '?'
dev_langs:
- C++
helpviewer_keywords:
- conditional operators [C++]
- '? : operator'
ms.assetid: 88643ee8-7100-4f86-880a-705ec22b6271
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 807754bb13f8302fe9583b6f4a8219e3aea81086
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="conditional-operator--"></a>条件演算子: しますか? :
## <a name="syntax"></a>構文  
  
```  
  
expression ? expression : expression  
```  
  
## <a name="remarks"></a>コメント  
 条件演算子 (**?:**) は三項演算子 (3 つのオペランドを受け取ります)。 条件演算子は次のように機能します。  
  
-   最初のオペランドは `bool` に暗黙的に変換されます。 これが評価され、すべての副作用が完了してから続行されます。  
  
-   最初のオペランドが評価された場合**true** (1)、2 番目のオペランドが評価されます。  
  
-   最初のオペランドが評価された場合**false** (0)、3 番目のオペランドが評価されます。  
  
 条件演算子の結果は、2 番目と 3 番目のどちらかのオペランドの評価の結果です。 条件式では、最後の 2 つのオペランドのうちの 1 つだけが評価されます。  
  
 条件式の結合規則は、右から左方向です。 最初のオペランドは整数またはポインター型である必要があります。 次の規則は、2 番目と 3 番目のオペランドに適用されます。  
  
-   両方のオペランドが同じ型である場合、結果もその型になります。  
  
-   両方のオペランドが演算型または列挙型の通常の算術変換がある場合 (「[標準変換](standard-conversions.md)) それら共通型に変換するために実行されます。  
  
-   両方のオペランドがポインター型である場合、または一方がポインター型でもう一方が 0 に評価される定数式である場合、それらを共通型に変換するためにポインター変換が実行されます。  
  
-   両方のオペランドが参照型である場合、参照変換が実行されてそれらは共通型に変換されます。  
  
-   両方のオペランドが void 型の場合は、共通型が void 型になります。  
  
-   両方のオペランドが同じユーザー定義型である場合、共通型はその型になります。  
  
-   オペランドの型が異なり、少なくとも 1 つのオペランドがユーザー定義型である場合、共通型を特定するために言語規則が使用されます (下記の警告を参照)。  
  
 上記のリストにない 2 番目と 3 番目のオペランドの組み合わせは無効です。 2 番目と 3 番目のオペランドが同じ型で両方が左辺値の場合は、結果の型は共通型であり、左辺値です。  
  
> [!WARNING]
>  2 番目と 3 番目のオペランドの型が同一でない場合は、C++ 標準で指定されている複合型の変換規則が呼び出されます。 これらの変換は、一時オブジェクトの構築と破棄など、予期しない動作をする可能性があります。 このため、次のいずれかを行うことを強くお勧めします。(1) 条件演算子のオペランドとしてユーザー定義型を使用することは避ける。(2) どうしてもユーザー定義型を使用する場合は、各オペランドを一般的な型に明示的にキャストする。  
  
## <a name="example"></a>例  
  
```  
// expre_Expressions_with_the_Conditional_Operator.cpp  
// compile with: /EHsc  
// Demonstrate conditional operator  
#include <iostream>  
using namespace std;  
int main() {  
   int i = 1, j = 2;  
   cout << ( i > j ? i : j ) << " is greater." << endl;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [C++ 組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [条件式演算子](../c-language/conditional-expression-operator.md)