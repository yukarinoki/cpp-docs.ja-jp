---
description: 詳細については、「コンパイラエラー C2131」を参照してください。
title: コンパイラエラー C2131
ms.date: 02/28/2019
f1_keywords:
- C2131
helpviewer_keywords:
- C2131
ms.openlocfilehash: 3c1f4e783c9341acf9e41fff99bba784acd8bbec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124177"
---
# <a name="compiler-error-c2131"></a>コンパイラエラー C2131

> 式が定数に評価されませんでした

またはとして宣言された式 **`const`** は、 **`constexpr`** コンパイル時に定数に評価されませんでした。 コンパイラは、使用されている時点で式の値を判別できる必要があります。

## <a name="example"></a>例

この例では、エラー C2131 の原因とその修正方法を示します。

```cpp
// c2131.cpp
// compile by using: cl /EHsc /W4 /c c2131.cpp

struct test
{
    static const int array_size; // To fix, init array_size here.
    int size_array[array_size];  // C2131
};

const int test::array_size = 42;
```

```Output
c2131.cpp
c2131.cpp(7): error C2131: expression did not evaluate to a constant
c2131.cpp(7): note: failure was caused by non-constant arguments or reference to a non-constant symbol
c2131.cpp(7): note: see usage of 'array_size'
```

## <a name="see-also"></a>関連項目

[const](../../cpp/const-cpp.md)<br/>
[constexpr](../../cpp/constexpr-cpp.md)<br/>
