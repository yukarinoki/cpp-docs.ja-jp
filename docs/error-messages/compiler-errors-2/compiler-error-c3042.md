---
title: コンパイラ エラー C3042
ms.date: 11/04/2016
f1_keywords:
- C3042
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
ms.openlocfilehash: deb3b8d6251316bceb71ce03f2bda88520bbb9b3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626799"
---
# <a name="compiler-error-c3042"></a>コンパイラ エラー C3042

'copyprivate' 句および 'nowait' 句は、OpenMP 'directive' ディレクティブで同時に使用することはできません

[copyprivate](../../parallel/openmp/reference/copyprivate.md) 句と [nowait](../../parallel/openmp/reference/nowait.md) 句は、指定されたディレクティブでは同時に使用できません。 このエラーを解決するには、 `copyprivate` 句か `nowait` 句の一方または両方を削除します。

次の例では C3042 が生成されます。

```
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