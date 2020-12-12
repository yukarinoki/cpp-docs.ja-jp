---
description: '詳細情報: true (C++)'
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: 6f3a9a183a30057ab3a013dad6e03458e6532658
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186455"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>構文

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>解説

このキーワードは、 [bool](../cpp/bool-cpp.md) 型の変数または条件式の2つの値のうちの1つです (条件式は、真のブール式になります)。 `i`が型である場合 **`bool`** 、ステートメントは `i = true;` に割り当てら **`true`** `i` れます。

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
