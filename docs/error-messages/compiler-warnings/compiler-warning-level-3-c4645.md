---
description: '詳細情報: コンパイラの警告 (レベル 3) C4645'
title: コンパイラの警告 (レベル 3) C4645
ms.date: 11/04/2016
f1_keywords:
- C4645
helpviewer_keywords:
- C4645
ms.assetid: fd7c1ddf-f0d0-4e10-bab9-ccb4c3476298
ms.openlocfilehash: 1002abfa66eddbf4891f9d57af96bf0b949cd483
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305300"
---
# <a name="compiler-warning-level-3-c4645"></a>コンパイラの警告 (レベル 3) C4645

__declspec(noreturn) で宣言された関数に return ステートメントがあります。

[Noreturn](../../cpp/noreturn.md)修飾子でマークされた関数に [return](../../cpp/program-termination.md)ステートメントが見つかりました **`__declspec`** 。 **`return`** ステートメントは無視されました。

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
