---
description: 詳細については、「コンパイラエラー C2275」を参照してください。
title: コンパイラ エラー C2275
ms.date: 11/04/2016
f1_keywords:
- C2275
helpviewer_keywords:
- C2275
ms.assetid: c1eafa71-48de-46e0-82f3-b575538ef205
ms.openlocfilehash: c6bc03c630a859c2f0913fd482f463071a21758c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134551"
---
# <a name="compiler-error-c2275"></a>コンパイラ エラー C2275

' identifier ': この型は式として不適切に使用されています

式では、 `->` 演算子を識別子と共に使用し **`typedef`** ます。

次の例では、C2275 が生成されます。

```cpp
// C2275.cpp
typedef struct S {
    int mem;
} *S_t;
void func1( int *parm );
void func2() {
    func1( &S_t->mem );   // C2275, S_t is a typedef
}
```
