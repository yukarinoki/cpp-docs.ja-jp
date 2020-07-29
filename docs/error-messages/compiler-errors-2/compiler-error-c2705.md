---
title: コンパイラエラー C2705
ms.date: 11/04/2016
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 65d9ed2458f43e6c9a697be02ffc9b831259624c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225437"
---
# <a name="compiler-error-c2705"></a>コンパイラエラー C2705

' label ': ' exception handler block ' スコープへのジャンプが正しくありません。

実行は、、、ブロック内のラベルにジャンプ **`try`** / **`catch`** `__try` / **`__except`** `__try` / **`__finally`** します。 詳細については、「[例外処理](../../cpp/exception-handling-in-visual-cpp.md)」を参照してください。

次の例では、C2705 が生成されます。

```cpp
// C2705.cpp
int main() {
goto trouble;
   __try {
      trouble: ;   // C2705
   }
   __finally {}

   // try the following line instead
   // trouble: ;
}
```
