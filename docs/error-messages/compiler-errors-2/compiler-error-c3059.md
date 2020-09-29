---
title: コンパイラ エラー C3059
ms.date: 11/04/2016
f1_keywords:
- C3059
helpviewer_keywords:
- C3059
ms.assetid: 57220324-8286-4cab-a1ab-45385eb1eae0
ms.openlocfilehash: 9b1efc0969373b6a91b0800ae71477b2371814bb
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501443"
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
