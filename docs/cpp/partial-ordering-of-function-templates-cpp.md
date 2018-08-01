---
title: 関数テンプレート (C++) の部分的な順序付け |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 75689c07718bf066105920b566087c08a220a7de
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408807"
---
# <a name="partial-ordering-of-function-templates-c"></a>関数テンプレートの部分的な順序付け (C++)

関数呼び出しの引数リストと一致する複数の関数テンプレートを使用できます。 C++ では、呼び出す関数を指定するために、関数テンプレートの部分的な順序が定義されています。 順序が部分的なのは、同等に特殊化されていると見なされるテンプレートが存在するためです。

コンパイラは、使用できる最も特殊化されたテンプレート関数を一致候補から選択します。 関数テンプレートは、型を受け取る場合など、 __T__とを別の関数テンプレート__T\*__ が使用できる、 __T\*__ バージョンといいます特殊化された複数あり、ジェネリックをお勧めする__T__両方は使用可能な一致としても、引数がポインター型では、バージョン。

1 つの関数テンプレート候補がより特殊化されたかどうかを確認するには、次の手順を使用します。

1. T1 および T2 の 2 つの関数テンプレートを考えます。

2. T1 内のパラメーターを架空の一意の型 X に置き換えます。

3. T1 のパラメーター リストで、T2 がそのパラメーター リストの有効なテンプレートであるかどうかを確認します。 暗黙の変換は無視します。

4. T1 と T2 を逆にして、同じ処理を繰り返します。

5. 1 つのテンプレートが他のテンプレートの有効なテンプレート引数リストであっても、その逆が当てはまらない場合、そのテンプレートは他のテンプレートよりも特殊化されていないと見なされます。 互い手順前フォーム有効な引数を使用して両方のテンプレートと見なされます、均等に特殊化する場合、あいまいな呼び出しの結果しようとするそれらを使用します。

6. 次の規則を使用します。

     1. 特定の型を受け取るテンプレートは、ジェネリック型引数を受け取るテンプレートよりも特殊化されます。

     2. のみをテンプレート__T\*__  1 つのみをよりも詳細な__T__仮定を入力するため、 __X\*__ に対して有効な引数が、__T__テンプレート引数が__X__に対して有効な引数ではありません、 __T\*__ テンプレート引数。

     3. __const T__よりも詳細な__T__ため、 __const X__に対して有効な引数は、 __T__テンプレート引数が__X__は有効な引数ではなく、 __const T__テンプレート引数。

     4. __const T\*__ よりも詳細な__T\*__ ため、 __const X\*__ に対して有効な引数は、 __T\*__ テンプレート引数が__X\*__ に対して有効な引数ではありません、 __const T\*__ テンプレート引数。

## <a name="example"></a>例

次の例では、標準で指定されているは動作します。

```cpp
// partial_ordering_of_function_templates.cpp
// compile with: /EHsc
#include <iostream>

extern "C" int printf(const char*,...);
template <class T> void f(T) {
   printf_s("Less specialized function called\n");
}

template <class T> void f(T*) {
   printf_s("More specialized function called\n");
}

template <class T> void f(const T*) {
   printf_s("Even more specialized function for const T*\n");
}

int main() {
   int i =0;
   const int j = 0;
   int *pi = &i;
   const int *cpi = &j;

   f(i);   // Calls less specialized function.
   f(pi);  // Calls more specialized function.
   f(cpi); // Calls even more specialized function.
   // Without partial ordering, these calls would be ambiguous.
}
```  
  
### <a name="output"></a>出力  
  
```Output  
Less specialized function called  
More specialized function called  
Even more specialized function for const T*  
```  
  
## <a name="see-also"></a>関連項目
 [関数テンプレート](../cpp/function-templates.md)