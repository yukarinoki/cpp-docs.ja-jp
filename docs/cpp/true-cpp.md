---
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: f6420d0abea8bac1d385c1cfdfd58a5500cf5bd3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87185841"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>構文

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>解説

このキーワードは、 [bool](../cpp/bool-cpp.md)型の変数または条件式の2つの値のうちの1つです (条件式は、真のブール式になります)。 `i`が型である場合 **`bool`** 、ステートメントは `i = true;` に割り当てら **`true`** `i` れます。

## <a name="example"></a>例

```cpp
// bool_true.cpp
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
