---
title: コンパイラの警告 (レベル 4) C4725
ms.date: 11/04/2016
f1_keywords:
- C4725
helpviewer_keywords:
- C4725
ms.assetid: effa0335-71c3-4b3b-8618-da4b9b46a95d
ms.openlocfilehash: 9da830133bbca2abcd5fa77339e698b35dae32f6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50455641"
---
# <a name="compiler-warning-level-4-c4725"></a>コンパイラの警告 (レベル 4) C4725

Pentium のモデルによっては、命令が不正確になります。

コードにインライン アセンブリ命令が含まれていますが、これは Pentium マイクロプロセッサのモデルによっては正確な結果が得られないことがあります。

次の例では C4725 が生成されます。

```
// C4725.cpp
// compile with: /W4
// processor: x86
double m32fp = 2.0003e-17;

void f() {
   __asm
   {
      FDIV m32fp   // C4725
   }
}

int main() {
}
```