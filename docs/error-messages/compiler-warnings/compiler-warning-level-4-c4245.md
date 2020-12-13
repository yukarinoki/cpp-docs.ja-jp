---
description: '詳細情報: コンパイラの警告 (レベル 4) C4245'
title: コンパイラの警告 (レベル 4) C4245
ms.date: 11/04/2016
f1_keywords:
- C4245
helpviewer_keywords:
- C4245
ms.assetid: 85083d53-9cc2-4d12-b58c-6dad28f15cbe
ms.openlocfilehash: 8e75c82ca775881d3ac2771a19f0f68b789e1940
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341699"
---
# <a name="compiler-warning-level-4-c4245"></a>コンパイラの警告 (レベル 4) C4245

> '*conversion*': '*type1*' から ' type1 ' への変換、符号付き/符号 *なしの不一致*

**`signed const`** 負の値を持つ型を型に変換しようとしました **`unsigned`** 。

次の例では、C4245 が生成されます。

```cpp
// C4245.cpp
// compile with: /W4 /c
const int i = -1;
unsigned int j = i; // C4245

const int k = 1;
unsigned int l = k; // okay

int m = -1;
unsigned int n = m; // okay

void Test(size_t i) {}

int main() {
   Test( -19 );   // C4245
}
```
