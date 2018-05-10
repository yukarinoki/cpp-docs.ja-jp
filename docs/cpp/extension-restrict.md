---
title: _ _restrict |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d96abd70990f1c01229004e9be000ec4e35a8595
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="restrict"></a>__restrict
同様に、 **_ _declspec ([制限](../cpp/restrict.md))** 修飾子、`__restrict`キーワードは、シンボルは、現在のスコープで別名を指定ではないことを示します。 `__restrict` キーワードは、`__declspec ( restrict )` 修飾子とは次の点で相違があります。  
  
-   `__restrict` キーワードは変数に対してのみ有効です。`__declspec ( restrict )` は関数の宣言と定義内でのみ有効です。  
  
-   `__restrict` は C99 仕様の `restrict` に似ていますが、`__restrict` は C++ または C プログラムで使用できます。  
  
-   `__restrict` が使用されていると、コンパイラは変数の非エイリアスのプロパティを伝達しません。 つまり、`__restrict` 変数を `__restrict` ではない変数に割り当てる場合、コンパイラは引き続き non-__restrict 変数のエイリアス化を許可します。 これは C99 仕様の `restrict` キーワードの動作とは異なります。  
  
 一般に、関数全体の動作に影響を及ぼす場合、キーワードよりも `__declspec ( restrict )` を使用する方が適切です。  
  
 Visual Studio 2015 以降では、C++ 参照で `__restrict` を使用できます。  
  
> [!NOTE]
>  持っている変数で使用すると、[揮発性](../cpp/volatile-cpp.md)キーワード、`volatile`が優先されます。  
  
## <a name="example"></a>例  
  
```  
// __restrict_keyword.c  
// compile with: /LD  
// In the following function, declare a and b as disjoint arrays  
// but do not have same assurance for c and d.  
void sum2(int n, int * __restrict a, int * __restrict b,   
          int * c, int * d) {  
   int i;  
   for (i = 0; i < n; i++) {  
      a[i] = b[i] + c[i];  
      c[i] = b[i] + d[i];  
    }  
}  
  
// By marking union members as __restrict, tell compiler that  
// only z.x or z.y will be accessed in any given scope.  
union z {  
   int * __restrict x;  
   double * __restrict y;  
};  
```  
  
## <a name="see-also"></a>関連項目  
 [キーワード](../cpp/keywords-cpp.md)