---
title: コンパイラの警告 (レベル 3) C4995 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4995
dev_langs:
- C++
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5ae389fef72681c6a8b31c9790c6773535f467d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053480"
---
# <a name="compiler-warning-level-3-c4995"></a>コンパイラの警告 (レベル 3) C4995

'function': 名前が非推奨の #pragma としてマークされました

コンパイラはプラグマでマークされた関数を見つけました[非推奨とされます](../../preprocessor/deprecated-c-cpp.md)します。 この関数は、将来のリリースではサポートされなくなる可能性があります。 使用すると、この警告をにできます、[警告](../../preprocessor/warning.md)プラグマ (次の例)。

## <a name="example"></a>例

次の例では、C4995 が生成されます。

```
// C4995.cpp
// compile with: /W3
#include <stdio.h>

// #pragma warning(disable : 4995)
void func1(void)
{
    printf("\nIn func1");
}

int main()
{
    func1();
    #pragma deprecated(func1)
    func1();   // C4995
}
```