---
title: コンパイラエラー C2702
ms.date: 11/04/2016
f1_keywords:
- C2702
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
ms.openlocfilehash: eb8a19bf5d29a2a0c69dc27e9b22f76df63ce8e8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216077"
---
# <a name="compiler-error-c2702"></a>コンパイラエラー C2702

__except が終了ブロックに含まれていない可能性があります

例外ハンドラー ( `__try` / **`__except`** ) をブロック内に入れ子にすることはできません **`__finally`** 。

次の例では、C2702 が生成されます。

```cpp
// C2702.cpp
// processor: x86 IPF
int Counter;
int main() {
   __try {}
   __finally {
      __try {}   // C2702
      __except( Counter ) {}   // C2702
   }
}
```
