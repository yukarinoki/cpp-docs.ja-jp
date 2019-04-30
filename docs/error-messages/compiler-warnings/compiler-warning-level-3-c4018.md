---
title: コンパイラの警告 (レベル 3) C4018
ms.date: 11/04/2016
f1_keywords:
- C4018
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
ms.openlocfilehash: 6436f62a06cbe931ca5b42751d60507f21675c5c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402373"
---
# <a name="compiler-warning-level-3-c4018"></a>コンパイラの警告 (レベル 3) C4018

'expression' : signed/unsigned mismatch

符号付きと符号なし数値を比較するには、符号付きの値を符号なしに変換するコンパイラが必要です。

符号付きと符号なし型をテストするときに 2 つの種類のいずれかをキャストする場合は、この警告を解決する可能性があります。

次の例では、C4018 が生成されます。

```
// C4018.cpp
// compile with: /W3
int main() {
   unsigned int uc = 0;
   int c = 0;
   unsigned int c2 = 0;

   if (uc < c) uc = 0;   // C4018

   // OK
   if (uc == c2) uc = 0;
}
```