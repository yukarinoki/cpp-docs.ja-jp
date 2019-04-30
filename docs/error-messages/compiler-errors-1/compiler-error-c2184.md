---
title: コンパイラ エラー C2184
ms.date: 11/04/2016
f1_keywords:
- C2184
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
ms.openlocfilehash: 146035134cc159b9e4271ce10c94f196098581b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385837"
---
# <a name="compiler-error-c2184"></a>コンパイラ エラー C2184

'type': __ except 式の型が無効です。整数でなければなりません

[__ except](../../c-language/try-except-statement-c.md) ステートメントで型を使用しましたが、その型は許可されていません。

次の例では C2184 が生成されます。

```
// C2184.cpp
void f() {
   int * p;
   __try{}
   __except(p){};   // C2184
}
```

考えられる解決方法:

```
// C2184b.cpp
// compile with: /c
void f() {
   int i = 0;
   __try{}
   __except(i){};
}
```