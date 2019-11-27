---
title: コンパイラの警告 (レベル 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: 4c31023fbcb36c53a7d0f5138c280ff12c4d495e
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541178"
---
# <a name="compiler-warning-level-3-c4995"></a>コンパイラの警告 (レベル 3) C4995

' function ': 名前が非推奨として #pragma としてマークされました

コンパイラは、プラグマが[非推奨](../../preprocessor/deprecated-c-cpp.md)としてマークされた関数を検出しました。 この関数は、将来のリリースではサポートされなくなる可能性があります。 [警告](../../preprocessor/warning.md)プラグマ (次の例を参照) を使用して、この警告をオフにすることができます。

## <a name="example"></a>使用例

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