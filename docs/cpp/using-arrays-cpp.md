---
title: 配列の使用 (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- arrays [C++]
ms.assetid: 7818a7fe-7e82-4881-a3d1-7d25162b7fc7
ms.openlocfilehash: 7f7a987a2b4c18e59dd058ccfc4375c304188398
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152749"
---
# <a name="using-arrays-c"></a>配列の使用 (C++)

配列添字演算子 (`[ ]`) を使用すると、配列の個々の要素にアクセスできます。 一次元配列が添字のない式で使用されている場合、配列名は配列の最初の要素へのポインターに評価されます。

```cpp
// using_arrays.cpp
int main() {
   char chArray[10];
   char *pch = chArray;   // Evaluates to a pointer to the first element.
   char   ch = chArray[0];   // Evaluates to the value of the first element.
   ch = chArray[3];   // Evaluates to the value of the fourth element.
}
```

多次元配列を使用すると、式でさまざまな組み合わせを使用できます。

```cpp
// using_arrays_2.cpp
// compile with: /EHsc /W1
#include <iostream>
using namespace std;
int main() {
   double multi[4][4][3];   // Declare the array.
   double (*p2multi)[3];
   double (*p1multi);

   cout << multi[3][2][2] << "\n";   // C4700 Use three subscripts.
   p2multi = multi[3];               // Make p2multi point to
                                     // fourth "plane" of multi.
   p1multi = multi[3][2];            // Make p1multi point to
                                     // fourth plane, third row
                                     // of multi.
}
```

上記のコードで`multi`、3 次元配列の型は、**二重**します。 `p2multi`型の配列を指すポインター**二重**の 3 つのサイズ。 この例では、配列が 1 つ、2 つ、および 3 つの添字と共に使用されています。 `cout` ステートメントのように、すべての添字を指定する方が一般的ですが、`cout` に続くステートメントのように、配列要素の特定のサブセットを選択した方が便利なこともあります。

## <a name="see-also"></a>関連項目

[配列](../cpp/arrays-cpp.md)