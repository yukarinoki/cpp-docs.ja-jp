---
title: コンパイラの警告 (レベル 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: c96db3d4bd1124c96b22363531b7739d0757b613
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624017"
---
# <a name="compiler-warning-level-1-c4508"></a>コンパイラの警告 (レベル 1) C4508

'function': 関数は、値を返す必要があります'void' の戻り値型と見なされます

関数には、指定された戻り値の型がありません。 この場合は、C4430 も発生し、コンパイラは、C4430 (既定値は int) によって報告された修正を実装します。

この警告を解決するには、関数の戻り値の型を明示的に宣言します。

次の例では、C4508 が生成されます。

```
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```