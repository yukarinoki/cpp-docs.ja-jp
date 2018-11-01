---
title: A.3 並行領域の使用
ms.date: 11/04/2016
ms.assetid: 575216a1-960a-47f7-9c82-7f660291fcfe
ms.openlocfilehash: 573c4f7c47c90bc6d567c4640360aa6abee5a48c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50458995"
---
# <a name="a3---using-parallel-regions"></a>A.3 並行領域の使用

`parallel`ディレクティブ ([セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの) 粒度が粗い並列プログラムで使用できます。 次の例では、並行領域内の各スレッドはグローバル配列のどの部分を決定`x`、操作スレッドの数に基づきます。

```
#pragma omp parallel shared(x, npoints) private(iam, np, ipoints)
{
    iam = omp_get_thread_num();
    np =  omp_get_num_threads();
    ipoints = npoints / np;
    subdomain(x, iam, ipoints);
}
```