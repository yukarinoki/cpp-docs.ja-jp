---
title: コンパイラの警告 (レベル 3) C4538
ms.date: 11/04/2016
f1_keywords:
- C4538
helpviewer_keywords:
- C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
ms.openlocfilehash: 81634ed45ad7d09a35f8399774920f6445628dee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569365"
---
# <a name="compiler-warning-level-3-c4538"></a>コンパイラの警告 (レベル 3) C4538

'type': この型での const/volatile 修飾子はサポートされていません

修飾子キーワード正しく適用されませんでしたを配列にします。 詳細については、「 [配列](../../windows/arrays-cpp-component-extensions.md)」を参照してください。

次の例では、C4538 が生成されます。

```
// C4538.cpp
// compile with: /clr /W3 /LD
const array<int> ^f1();   // C4538
array<const int> ^f2();   // OK
```