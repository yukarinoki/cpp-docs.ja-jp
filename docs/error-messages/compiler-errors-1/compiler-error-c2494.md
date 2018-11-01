---
title: コンパイラ エラー C2494
ms.date: 11/04/2016
f1_keywords:
- C2494
helpviewer_keywords:
- C2494
ms.assetid: 5dfd07ab-351d-49c9-b54e-f0a104776ab8
ms.openlocfilehash: 0a8be1dd5ce8d906bc4d0b1ce72295a57f68b6cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507706"
---
# <a name="compiler-error-c2494"></a>コンパイラ エラー C2494

'keyword' は、フィルター式内から呼び出すことはできませんまたは _ _finally/finally にブロック

使用することはできません`keyword`で、`__finally`または finally ブロックします。

次の例では、C2494 が生成されます。

```
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

C2494 を使用する場合にも発生することが **/clr**します。

```
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