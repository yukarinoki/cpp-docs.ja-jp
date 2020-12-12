---
description: 詳細については、「コンパイラエラー C2319」を参照してください。
title: コンパイラ エラー C2319
ms.date: 11/04/2016
f1_keywords:
- C2319
helpviewer_keywords:
- C2319
ms.assetid: 25263e6e-f5ba-4d2c-8727-8c2d8ca2e5ce
ms.openlocfilehash: 54ee91245b4346837e6cfbdac2c9ab979556bfdd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268237"
---
# <a name="compiler-error-c2319"></a>コンパイラ エラー C2319

'try/catch' の後に複合ステートメントを指定する必要があります。 '{' が必要です

また **`try`** は **`catch`** ステートメントの後に、またはブロックが見つかりません **`try`** **`catch`** 。 ブロックは中かっこで囲む必要があります。

次の例では C2319 が生成されます。

```cpp
// C2319.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
   try {
      throw "ooops!";
   }
   catch( C ) ;    // C2319
   // try the following line instead
   // catch( C ) {}
}
```
