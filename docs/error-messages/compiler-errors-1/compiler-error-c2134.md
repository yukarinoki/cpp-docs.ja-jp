---
title: コンパイラ エラー C2134
ms.date: 11/04/2016
f1_keywords:
- C2134
ms.assetid: d45cb3e8-0be4-4bd6-8be9-5f8d2384363f
ms.openlocfilehash: 8bb472cc7864e597404394ac7c80468e1cd59f5c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595937"
---
# <a name="compiler-error-c2134"></a>コンパイラ エラー C2134

'function': 定数式の呼び出しは行われません

Constexpr ではその他の関数を呼び出すことができますのみとして宣言された関数は constexpr として宣言します。

次の例では、C2134 が生成されます。

```
// C2134.cpp
// compile with: /c
int A() {
    return 42;
};

constexpr int B() {
    return A();  // Error C2134: 'A': call does not result in a constant expression.
}
```

考えられる解決方法:

```
// C2134b.cpp
constexpr int A() {  // add constexpr to A, since it meets the requirements of constexpr.
    return 42;
};

constexpr int B() {
    return A();  // No error
}
```