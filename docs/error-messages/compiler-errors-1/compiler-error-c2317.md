---
title: コンパイラ エラー C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: 95444951106d74d01efe84f829b606eb2c547c99
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221264"
---
# <a name="compiler-error-c2317"></a>コンパイラ エラー C2317

'number' 行目で始まっている 'try' ブロックには catch ハンドラーがありません

ブロックには、 **`try`** 少なくとも1つの catch ハンドラーが必要です。

次の例では C2317 が生成されます。

```cpp
// C2317.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   // C2317, no catch handler
}
```

考えられる解決策:

```cpp
// C2317b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "throw an exception";
   }
   catch(char*) {}
}
```
