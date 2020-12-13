---
description: '詳細情報: コンパイラの警告 (レベル 4) C4740'
title: コンパイラの警告 (レベル 4) C4740
ms.date: 11/04/2016
f1_keywords:
- C4740
helpviewer_keywords:
- C4740
ms.assetid: 85528969-966a-44b4-8a2f-971704c64477
ms.openlocfilehash: 31c25660177931e468681f3e563a9885ca1faa01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330534"
---
# <a name="compiler-warning-level-4-c4740"></a>コンパイラの警告 (レベル 4) C4740

インライン asm コードの内外のフローにより、グローバルな最適化が抑制される

ブロックへのジャンプがある場合 **`asm`** 、その関数のグローバル最適化は無効になります。

次の例では、C4740 が生成されます。

```cpp
// C4740.cpp
// compile with: /O2 /W4
// processor: x86
int main() {
   __asm jmp tester
   tester:;
}
```
