---
title: A.28 num_threads 句の使用
ms.date: 11/04/2016
ms.assetid: 26238da1-902c-49b4-9559-0fbc9eaf7f36
ms.openlocfilehash: 99dd327d0a97f561107ffaa6a6ed1435e3772a41
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492287"
---
# <a name="a28---use-of-numthreads-clause"></a>A.28 num_threads 句の使用

次の例で、`num_threads`句 ([セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) [8] ページ)。 並列領域は、最大 10 個のスレッドで実行されます。

```
#include <omp.h>
main()
{
    omp_set_dynamic(1);
    ...
    #pragma omp parallel num_threads(10)
    {
        ... parallel region ...
    }
}
```