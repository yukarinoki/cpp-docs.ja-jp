---
description: 詳細については、「コンパイラエラー C2134」を参照してください。
title: コンパイラエラー C2134
ms.date: 11/04/2016
f1_keywords:
- C2134
ms.assetid: d45cb3e8-0be4-4bd6-8be9-5f8d2384363f
ms.openlocfilehash: 16149c3b3f28720670c26f0fae2a89d1b7b6f8b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323111"
---
# <a name="compiler-error-c2134"></a>コンパイラエラー C2134

' function ': 呼び出しは定数式ではありません

Constexpr として宣言された関数は、constexpr として宣言された他の関数を呼び出すことができます。

次の例では、C2134 が生成されます。

```cpp
// C2134.cpp
// compile with: /c
int A() {
    return 42;
};

constexpr int B() {
    return A();  // Error C2134: 'A': call does not result in a constant expression.
}
```

考えられる解決策:

```cpp
// C2134b.cpp
constexpr int A() {  // add constexpr to A, since it meets the requirements of constexpr.
    return 42;
};

constexpr int B() {
    return A();  // No error
}
```
