---
title: コンパイラの警告 (レベル 1) C4405
ms.date: 11/04/2016
f1_keywords:
- C4405
helpviewer_keywords:
- C4405
ms.assetid: 155c64d6-58ae-4455-b61f-ccd711c5da96
ms.openlocfilehash: e85bdc995fe16f91e2e9c734dacc65ca0b7b622d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654914"
---
# <a name="compiler-warning-level-1-c4405"></a>コンパイラの警告 (レベル 1) C4405

'identifier': 識別子は予約語

インライン アセンブリの予約語は、変数名として使用されます。 予期しない結果がある可能性があります。 この警告を解決するには、インライン アセンブリの予約語で名前付けの変数をしないでください。 次の例では、C4405 が生成されます。

```
// C4405.cpp
// compile with: /W1
// processor: x86
void func1() {
   int mov = 0, i = 0;
   _asm {
      mov mov, 0;   // C4405
      // instead, try ..
      // mov i, 0;
   }
}

int main() {
}
```