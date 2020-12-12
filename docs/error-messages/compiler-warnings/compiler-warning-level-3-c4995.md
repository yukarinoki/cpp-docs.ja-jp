---
description: '詳細情報: コンパイラの警告 (レベル 3) C4995'
title: コンパイラの警告 (レベル 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: bb63802edf523fb0816bc6aeec289839b99b1110
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332050"
---
# <a name="compiler-warning-level-3-c4995"></a>コンパイラの警告 (レベル 3) C4995

' function ': 名前が非推奨として #pragma としてマークされました

コンパイラは、プラグマが [非推奨](../../preprocessor/deprecated-c-cpp.md)としてマークされた関数を検出しました。 この関数は、将来のリリースではサポートされなくなる可能性があります。 [警告](../../preprocessor/warning.md)プラグマ (次の例を参照) を使用して、この警告をオフにすることができます。

## <a name="example"></a>例

次の例では、C4995 が生成されます。

```cpp
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
