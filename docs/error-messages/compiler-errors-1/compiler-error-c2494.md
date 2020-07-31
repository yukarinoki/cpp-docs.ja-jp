---
title: コンパイラ エラー C2494
ms.date: 11/04/2016
f1_keywords:
- C2494
helpviewer_keywords:
- C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
ms.openlocfilehash: e337e5b54706c1ae9d566131c98fd178c523f87e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216181"
---
# <a name="compiler-error-c2494"></a>コンパイラ エラー C2494

> '*keyword*' は、フィルター式または __finally/finally ブロック内から呼び出すことはできません。

*キーワード*を **`__finally`** またはブロックで使用することはできません **`finally`** 。

次の例では、C2494 が生成されます。

```cpp
// C2494.cpp
#include <malloc.h>

int main() {
   __try {}
   __except ( _alloca(100), 1 ) {}   // C2494
   __try {}
   __finally {
      _alloca(100);   // C2494
   }
}
```

C2494 は、 **/clr**を使用しているときにも発生する可能性があります。

```cpp
// C2494b.cpp
// compile with: /clr
#include <malloc.h>

int main() {
   char * buf;
   try {}
   catch (char * buf2) {}
   finally {
      _alloca(100);   // C2494
   }
}
```
