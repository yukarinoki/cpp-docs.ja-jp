---
description: 詳細については、「コンパイラエラー C2494」を参照してください。
title: コンパイラ エラー C2494
ms.date: 11/04/2016
f1_keywords:
- C2494
helpviewer_keywords:
- C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
ms.openlocfilehash: 4842ad7360b4d8a943ee118cb56d79b694232c84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283655"
---
# <a name="compiler-error-c2494"></a>コンパイラ エラー C2494

> '*keyword*' は、フィルター式または __finally/finally ブロック内から呼び出すことはできません。

*キーワード* を **`__finally`** またはブロックで使用することはできません **`finally`** 。

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

C2494 は、 **/clr** を使用しているときにも発生する可能性があります。

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
