---
title: '関係演算子: &lt;、 &gt;、 &lt;=、および&gt;= |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- <
- '>'
dev_langs:
- C++
helpviewer_keywords:
- '> operator'
- less than operator
- relational operators [C++], syntax
- '>= operator'
- greater than or equal to operators [C++]
- greater than operators [C++]
- < operator
- less than or equal to operator
- <= operator
ms.assetid: d346b53d-f14d-4962-984f-89d39a17ca0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56372764c70498aec4ccf7b23fc7d074d1df179e
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/10/2018
ms.locfileid: "37943517"
---
# <a name="relational-operators-lt-gt-lt-and-gt"></a>関係演算子: &lt;、 &gt;、 &lt;=、および &gt;=
## <a name="syntax"></a>構文  
  
```  
expression < expression  
expression > expression  
expression <= expression  
expression >= expression  
```  
  
## <a name="remarks"></a>Remarks  
 二項関係演算子は次のリレーションシップを判断します。  
  
-   小さい (**\<**)  
  
-   大きい (**>**)  
  
-   等しいまたはそれよりも小さい (**\<=**)  
  
-   大きいまたは等しい (**>=**)  
  
 関係演算子の結合規則は、左から右方向です。 関係演算子のオペランドは、両方とも数値型またはポインター型である必要があります。 型の値を生成する**bool**します。 返される値**false** (0)、式内のリレーションシップが false、それ以外の場合、返される値は**true** (1)。  
  
## <a name="example"></a>例  
  
```cpp 
// expre_Relational_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << "The true expression 3 > 2 yields: "  
         << (3 > 2) << endl  
         << "The false expression 20 < 10 yields: "  
         << (20 < 10) << endl;  
}  
```  
  
 上記の例の式のため、かっこで囲む必要があります、ストリーム挿入演算子 (**<<**) が関係演算子より高い優先順位。 したがって、かっこがない最初の式は次のように評価されます。  
  
```cpp 
(cout << "The true expression 3 > 2 yields: " << 3) < (2 << "\n");  
```  
  
 通常の算術変換は、「[標準変換](standard-conversions.md)数値型オペランドに適用されます。  
  
## <a name="comparing-pointers"></a>ポインターの比較  
 同じ型のオブジェクトへの 2 つのポインターを比較する場合、結果はプログラムのアドレス空間で指すオブジェクトの位置によって決まります。 ポインターは、0 または void * 型のポインターに評価される定数式と比較することもできます。 ポインターの比較ができるかどうかの型のポインターに対して void \*、他のポインターは暗黙的に void 型へ変換\*します。 次に、比較が行われます。  
  
 次の場合を除いて、異なる型の 2 つのポインターを比較することはできません。  
  
-   1 つの型が、他の型の派生クラス型である。  
  
-   ポインターのうち少なくとも 1 つが void * 型に明示的に変換 (キャスト) される  (その他のポインターは暗黙的に void 型へ変換\*変換します)。  
  
 同じオブジェクトを指す同じ型の 2 つのポインターは、等しい結果になることが保証されています。 オブジェクトの非静的メンバーへの 2 つのポインターを比較する場合、次の規則が適用されます。  
  
-   クラス型、共用体でない場合とで 2 つのメンバーが区切られていない場合、*アクセス指定子*public、protected、または、private などに宣言されたメンバーへのポインター最後は比較に宣言されたメンバーへのポインターより大きい先ほどの。  
  
-   2 つのメンバーで区切られている場合、*アクセス指定子*結果は定義されていません。  
  
-   クラス型が共用体である場合は、その共用体の異なるデータ メンバーへのポインターが等しいと見なされます。  
  
 2 個のポインターが、同じ配列の要素、または配列の末尾の次の位置の要素をポイントしている場合、より上位の添字を持つオブジェクトへのポインターが高く評価されます。 ポインターの比較は、ポインターが同じ配列のオブジェクトまたは配列の末尾の次の位置を参照している場合にのみ、有効であると保証されます。  
  
## <a name="see-also"></a>関連項目  
 [二項演算子を含む式](../cpp/expressions-with-binary-operators.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [C 関係演算子と等値演算子](../c-language/c-relational-and-equality-operators.md)