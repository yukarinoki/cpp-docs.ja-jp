---
title: コンパイラ エラー C2317
ms.date: 11/04/2016
f1_keywords:
- C2317
helpviewer_keywords:
- C2317
ms.assetid: e44d129b-8d3e-4ce9-9d79-6791ee77f25e
ms.openlocfilehash: 637433ee22ee77a7106e3692a39eec9973d979c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350596"
---
# <a name="compiler-error-c2317"></a>コンパイラ エラー C2317

'number' 行目で始まっている 'try' ブロックには catch ハンドラーがありません

`try` ブロックには少なくとも 1 つの catch ハンドラーが必要です。

次の例では C2317 が生成されます。

```
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

考えられる解決方法:

```
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