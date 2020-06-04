---
title: コンパイラの警告 (レベル 1) C4508
ms.date: 11/04/2016
f1_keywords:
- C4508
helpviewer_keywords:
- C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
ms.openlocfilehash: 54baf35eaeb5ef2c8add024f25c059480d60617b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186568"
---
# <a name="compiler-warning-level-1-c4508"></a>コンパイラの警告 (レベル 1) C4508

' function ': 関数は値を返す必要があります。戻り値の型として ' void ' が想定されます

関数には、戻り値の型が指定されていません。 この場合、C4430 も起動し、コンパイラは C4430 によって報告された修正プログラムを実装します (既定値は int です)。

この警告を解決するには、関数の戻り値の型を明示的に宣言します。

次の例では、C4508 が生成されます。

```cpp
// C4508.cpp
// compile with: /W1 /c
#pragma warning (disable : 4430)
func() {}   // C4508
void func2() {}   // OK
```
