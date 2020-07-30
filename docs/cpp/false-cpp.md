---
title: false (C++)
ms.date: 11/04/2016
f1_keywords:
- false_cpp
helpviewer_keywords:
- false keyword [C++]
ms.assetid: cc13aec5-1f02-4d38-8dbf-5473ea2b354f
ms.openlocfilehash: d6162bdde3dea0d245a0c83c1d52b06003fee16c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87227492"
---
# <a name="false-c"></a>false (C++)

キーワードは、 [bool](../cpp/bool-cpp.md)型の変数または条件式の2つの値のいずれかです (条件式は、 **`true`** ブール式になります)。 たとえば、 `i` が型の変数である場合、 **`bool`** `i = false;` ステートメントはに割り当てら **`false`** `i` れます。

## <a name="example"></a>例

```cpp
// bool_false.cpp
#include <stdio.h>

int main()
{
    bool bb = true;
    printf_s("%d\n", bb);
    bb = false;
    printf_s("%d\n", bb);
}
```

```Output
1
0
```

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)
