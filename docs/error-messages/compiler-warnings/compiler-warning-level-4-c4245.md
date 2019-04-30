---
title: コンパイラの警告 (レベル 4) C4245
ms.date: 11/04/2016
f1_keywords:
- C4245
helpviewer_keywords:
- C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
ms.openlocfilehash: 7f22386439803de1b59f3236775aa6cec0254eab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400995"
---
# <a name="compiler-warning-level-4-c4245"></a>コンパイラの警告 (レベル 4) C4245

'conversion': 'type1' から 'type2'、符号付き/符号なしの不一致への変換

符号付き変換しようとしています。 **const**に負の値を持つ、`unsigned`します。

次の例では、C4245 が生成されます。

```
// C4245.cpp
// compile with: /W4 /c
const int i = -1;
unsigned int j = i; // C4245

const int k = 1;
unsigned int l = k; // okay

int m = -1;
unsigned int n = m; // okay

void Test(size_t i) {}

int main() {
   Test( -19 );   // C4245
}
```