---
title: true (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- true_cpp
dev_langs:
- C++
helpviewer_keywords:
- true keyword [C++]
ms.assetid: 96be2a70-51c3-4250-9752-874d25a5a11e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e43fbfd9b3cff9ea617238ed7b4cccd08f780cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018705"
---
# <a name="true-c"></a>true (C++)

## <a name="syntax"></a>構文

```
bool-identifier = true ;
bool-expression logical-operator true ;
```

## <a name="remarks"></a>Remarks

このキーワードは、2 つの型の変数値のいずれかの[bool](../cpp/bool-cpp.md)または条件式 (条件式は true ブール式ではようになりました)。 場合`i`の種類は**bool**、then ステートメント`i = true;`割り当てます**true**に`i`します。

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