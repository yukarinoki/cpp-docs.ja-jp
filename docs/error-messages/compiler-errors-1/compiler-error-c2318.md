---
title: コンパイラ エラー C2318
ms.date: 11/04/2016
f1_keywords:
- C2318
helpviewer_keywords:
- C2318
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
ms.openlocfilehash: 5f608d0407c24bd01ed7b80dbef873dd30662661
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221251"
---
# <a name="compiler-error-c2318"></a>コンパイラ エラー C2318

この catch ハンドラーと関連付けられた try ブロックはありません。

**`catch`** ハンドラーが定義されていますが、その前にブロックがありません **`try`** 。

次の例では C2318 が生成されます。

```cpp
// C2318.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   // no try block
   catch( int ) {}   // C2318
}
```

考えられる解決策:

```cpp
// C2318b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try{}
   catch( int ) {}
}
```
