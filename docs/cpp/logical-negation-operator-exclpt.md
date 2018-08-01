---
title: '論理否定演算子: ! | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '!'
- Not
dev_langs:
- C++
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f911c6f01dfc188c26355a3749d8a130f0d6951
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403590"
---
# <a name="logical-negation-operator-"></a>論理否定演算子: !
## <a name="syntax"></a>構文  
  
```  
! cast-expression  
```  
  
## <a name="remarks"></a>Remarks  
 論理否定演算子 (**!**)、オペランドの意味を反転させます。 オペランドは、数値型またはポインター型 (または、数値型またはポインター型に評価される式) である必要があります。 オペランドは型に暗黙的に変換されます**bool**します。 変換後のオペランドが FALSE 以外の場合、結果は TRUE変換後のオペランドが TRUE の場合、結果は FALSE です。 結果は型**bool**します。  
  
 式の*e*、単項式 **! * * * e*が、式と同じ **(* * * e* `==` 0)、オーバー ロードされた演算子が関係する場所を除く。  
  
## <a name="operator-keyword-for-"></a>! の演算子キーワード  
 **いない**演算子と等価のテキストは、 **!** します。 アクセスする 2 つの方法がある、**いない**プログラムで演算子: ヘッダー ファイルをインクルード`iso646.h`、使用してコンパイル、 [/Za](../build/reference/za-ze-disable-language-extensions.md) (言語拡張を無効にする) コンパイラ オプション。  
  
## <a name="example"></a>例  
  
```cpp 
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [単項演算子を含む式](../cpp/expressions-with-unary-operators.md)   
 [C++ の組み込み演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [単項算術演算子](../c-language/unary-arithmetic-operators.md)