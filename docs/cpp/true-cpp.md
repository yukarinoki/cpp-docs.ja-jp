---
title: true (C++)
ms.date: 11/04/2016
f1_keywords:
- true_cpp
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
ms.openlocfilehash: b497c3c9eb1b30074c9b7286c438d0077525e05b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188039"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>構文

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>解説

このキーワードは、 [bool](../cpp/bool-cpp.md)型の変数または条件式の2つの値のうちの1つです (条件式は、真のブール式になります)。 `i` が**bool**型の場合、ステートメント `i = true;` `i`に**true**が割り当てられます。

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

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)
