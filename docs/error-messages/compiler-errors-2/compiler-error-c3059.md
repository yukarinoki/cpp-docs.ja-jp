---
description: 詳細については、「コンパイラエラー C3059」を参照してください。
title: コンパイラ エラー C3059
ms.date: 11/04/2016
f1_keywords:
- C3059
helpviewer_keywords:
- C3059
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
ms.openlocfilehash: 82629fb77a0cf589f4e311d951fcf1540e0b7c8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281757"
---
# <a name="compiler-error-c3059"></a>コンパイラ エラー C3059

'var' : 'threadprivate' シンボルは 'clause' 句の中で使用することはできません

[threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) シンボルが句の中で使用されました。

次の例では C3059 が生成されます。

```cpp
// C3059.cpp
// compile with: /openmp
#include "omp.h"
int x, y;
#pragma omp threadprivate(x, y)

int main() {
   #pragma omp parallel private(x, y)   // C3059
   {
      x = y;
   }
}
```

考えられる解決策:

```cpp
// C3059b.cpp
// compile with: /openmp
#include "omp.h"
int x = 0, y = 0;

int main() {
   #pragma omp parallel firstprivate(y) private(x)
   {
      x = y;
   }
}
```
