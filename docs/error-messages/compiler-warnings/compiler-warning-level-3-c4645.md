---
title: コンパイラの警告 (レベル 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: a3e5c834a3f14b9a125176dcddd5bcc355cf1faa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401645"
---
# <a name="compiler-warning-level-3-c4645"></a>コンパイラの警告 (レベル 3) C4645

__declspec(noreturn) で宣言された関数に return ステートメントがあります。

A[返す](../../cpp/return-statement-in-program-termination-cpp.md)でマークされている関数に含まれて、 [noreturn](../../cpp/noreturn.md) `__declspec`修飾子。 `return` ステートメントは無視されました。

次の例では C4645 が生成されます。

```
// C4645.cpp
// compile with:  /W3
void __declspec(noreturn) func() {
   return;   // C4645, delete this line to resolve
}

int main() {
}
```