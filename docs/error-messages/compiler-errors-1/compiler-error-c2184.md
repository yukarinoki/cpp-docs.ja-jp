---
description: 詳細については、「コンパイラエラー C2184」を参照してください。
title: コンパイラ エラー C2184
ms.date: 11/04/2016
f1_keywords:
- C2184
helpviewer_keywords:
- C2184
ms.assetid: 80fc8bff-7d76-4bde-94d2-01d84bb6824a
ms.openlocfilehash: 26513ff4162023398336eae3396e7be6abb8f8a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335145"
---
# <a name="compiler-error-c2184"></a>コンパイラ エラー C2184

'type': __ except 式の型が無効です。整数でなければなりません

[__ except](../../c-language/try-except-statement-c.md) ステートメントで型を使用しましたが、その型は許可されていません。

次の例では C2184 が生成されます。

```cpp
// C2184.cpp
void f() {
   int * p;
   __try{}
   __except(p){};   // C2184
}
```

考えられる解決策:

```cpp
// C2184b.cpp
// compile with: /c
void f() {
   int i = 0;
   __try{}
   __except(i){};
}
```
