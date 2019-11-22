---
title: コンパイラの警告 (レベル 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: 4fa286f177284c03e5067b4af56f4e606b073653
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189375"
---
# <a name="compiler-warning-level-3-c4645"></a>コンパイラの警告 (レベル 3) C4645

__declspec(noreturn) で宣言された関数に return ステートメントがあります。

A [return](../../cpp/return-statement-in-program-termination-cpp.md) statement was found in a function that is marked with the [noreturn](../../cpp/noreturn.md) `__declspec` modifier. `return` ステートメントは無視されました。

次の例では C4645 が生成されます。

```cpp
// C4645.cpp
// compile with:  /W3
void __declspec(noreturn) func() {
   return;   // C4645, delete this line to resolve
}

int main() {
}
```