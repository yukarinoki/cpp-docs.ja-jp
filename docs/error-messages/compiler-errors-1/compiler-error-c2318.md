---
title: コンパイラ エラー C2318
ms.date: 11/04/2016
f1_keywords:
- C2318
helpviewer_keywords:
- C2318
ms.assetid: 169e30b9-df78-46cb-90bf-576ad3c32fd4
ms.openlocfilehash: a68a333c9cb817a653597acb011dfbb9291c4d0e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350583"
---
# <a name="compiler-error-c2318"></a>コンパイラ エラー C2318

この catch ハンドラーと関連付けられた try ブロックはありません。

`catch` ハンドラーが定義されていますが、その前に `try` ブロックがありません。

次の例では C2318 が生成されます。

```
// C2318.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   // no try block
   catch( int ) {}   // C2318
}
```

考えられる解決方法:

```
// C2318b.cpp
// compile with: /EHsc
#include <eh.h>
int main() {
   try{}
   catch( int ) {}
}
```