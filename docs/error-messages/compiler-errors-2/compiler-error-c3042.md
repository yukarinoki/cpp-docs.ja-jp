---
description: 詳細については、「コンパイラエラー C3042」を参照してください。
title: コンパイラ エラー C3042
ms.date: 11/04/2016
f1_keywords:
- C3042
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
ms.openlocfilehash: 04c4366e574f158234653d32b4b6e01bfceaaa27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269914"
---
# <a name="compiler-error-c3042"></a>コンパイラ エラー C3042

'copyprivate' 句および 'nowait' 句は、OpenMP 'directive' ディレクティブで同時に使用することはできません

[copyprivate](../../parallel/openmp/reference/openmp-clauses.md#copyprivate) 句と [nowait](../../parallel/openmp/reference/openmp-clauses.md#nowait) 句は、指定されたディレクティブでは同時に使用できません。 このエラーを解決するには、 `copyprivate` 句か `nowait` 句の一方または両方を削除します。

次の例では C3042 が生成されます。

```cpp
// C3042.cpp
// compile with: /openmp /c
#include <stdio.h>
#include "omp.h"

double d;

int main() {
    #pragma omp parallel private(d)
   {
      #pragma omp single copyprivate(d) nowait   // C3042
      {
      }
   }
}
```
