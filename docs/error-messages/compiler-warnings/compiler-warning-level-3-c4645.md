---
title: コンパイラの警告 (レベル 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: 607122b5592c9db4fc2ad4cabf369b4605b2673b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228766"
---
# <a name="compiler-warning-level-3-c4645"></a>コンパイラの警告 (レベル 3) C4645

__declspec(noreturn) で宣言された関数に return ステートメントがあります。

[Noreturn](../../cpp/noreturn.md)修飾子でマークされた関数に[return](../../cpp/return-statement-in-program-termination-cpp.md)ステートメントが見つかりました **`__declspec`** 。 **`return`** ステートメントは無視されました。

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
