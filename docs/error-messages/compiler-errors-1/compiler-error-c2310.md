---
title: コンパイラ エラー C2310
ms.date: 11/04/2016
f1_keywords:
- C2310
helpviewer_keywords:
- C2310
ms.assetid: 1969c682-b97e-43fb-b9a9-f783e7ff1710
ms.openlocfilehash: 8bd885a730bfe4890e99fa9ec7beb83169aca4d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560684"
---
# <a name="compiler-error-c2310"></a>コンパイラ エラー C2310

catch ハンドラーは、1 つの型を指定する必要があります。

Catch ハンドラーは、型を持たないまたは複数の種類を指定します。

次の例では、C2310 が生成されます。

```
// C2310.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try {
      throw "Out of memory!";
   }
   catch( int ,int) {}   // C2310 two types
   // try the following line instead
   // catch( int)  {}
}
```