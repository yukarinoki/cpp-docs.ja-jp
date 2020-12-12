---
description: 詳細については、「コンパイラエラー C2090」を参照してください。
title: コンパイラエラー C2090
ms.date: 11/04/2016
f1_keywords:
- C2090
helpviewer_keywords:
- C2090
ms.assetid: e8176e55-382b-453d-aa27-6597f0274afd
ms.openlocfilehash: 224f900a20d57a35a6a6c6dcc2dc95b09c596403
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251909"
---
# <a name="compiler-error-c2090"></a>コンパイラエラー C2090

関数は配列を返します

関数は配列を返すことができません。 代わりに、配列へのポインターを返します。

次の例では、C2090 が生成されます。

```cpp
// C2090.cpp
int func1(void)[] {}   // C2090
```

考えられる解決策:

```cpp
// C2090b.cpp
// compile with: /c
int* func2(int * i) {
   return i;
}
```
