---
description: '詳細情報: 関数テンプレートの部分的な順序付け (C++)'
title: 関数テンプレートの部分的な順序付け (C++)
ms.date: 07/30/2019
helpviewer_keywords:
- partial ordering of function templates
ms.assetid: 0c17347d-0e80-47ad-b5ac-046462d9dc73
ms.openlocfilehash: 701c97aa819d0294f69f2fe2a71ffb9bf0210afa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145900"
---
# <a name="partial-ordering-of-function-templates-c"></a>関数テンプレートの部分的な順序付け (C++)

関数呼び出しの引数リストと一致する複数の関数テンプレートを使用できます。 C++ では、呼び出す関数を指定するために、関数テンプレートの部分的な順序が定義されています。 順序が部分的なのは、同等に特殊化されていると見なされるテンプレートが存在するためです。

コンパイラは、使用できる最も特殊化されたテンプレート関数を一致候補から選択します。 たとえば、関数テンプレートが型を受け取り、を `T` 受け取る別の関数テンプレート `T*` が使用可能な場合、その `T*` バージョンはより特殊化されていると言います。 引数がポインター型である場合は、 `T` 両方とも一致する可能性があっても、ジェネリックバージョンよりも優先されます。

1 つの関数テンプレート候補がより特殊化されたかどうかを確認するには、次の手順を使用します。

1. T1 および T2 の 2 つの関数テンプレートを考えます。

1. T1 内のパラメーターを架空の一意の型 X に置き換えます。

1. T1 のパラメーター リストで、T2 がそのパラメーター リストの有効なテンプレートであるかどうかを確認します。 暗黙の変換は無視します。

1. T1 と T2 を逆にして、同じ処理を繰り返します。

1. あるテンプレートが他のテンプレートに対して有効なテンプレート引数リストであっても、逆の場合は、そのテンプレートは他のテンプレートよりも特殊化されていると見なされます。 前の手順を使用した場合、両方のテンプレートで有効な引数が相互に有効であると見なされます。これらのテンプレートは、同じように特殊化されていると見なされ、それらを使用しようとするとあいまいな呼び出しの結果になります。

1. 次の規則を使用します。

   1. 特定の型を受け取るテンプレートは、ジェネリック型引数を受け取るテンプレートよりも特殊化されます。

   1. `T*` `T` 架空の型 `X*` はテンプレート引数の有効な引数であるものの、テンプレート `T` 引数の有効な引数で `X` はないため、 `T*` 使用するテンプレートはより特殊化されたものにすぎません。

   1. `const T` はより特殊化されてい `T` `const X` ます。はテンプレート引数の有効な引数ですが、 `T` `X` テンプレート引数の有効な引数ではありません `const T` 。

   1. `const T*` はより特殊化されてい `T*` `const X*` ます。はテンプレート引数の有効な引数ですが、 `T*` `X*` テンプレート引数の有効な引数ではありません `const T*` 。

## <a name="example"></a>例

次のサンプルは、標準で指定されているとおりに動作します。

```cpp
// partial_ordering_of_function_templates.cpp
// compile with: /EHsc
#include <iostream>

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
