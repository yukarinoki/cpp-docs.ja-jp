---
title: A.12 atomic ディレクティブの使用
ms.date: 11/04/2016
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
ms.openlocfilehash: 0f75b182e2cae11f0e72d5ca1e67f887294e8f69
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50504442"
---
# <a name="a12---using-the-atomic-directive"></a>A.12 atomic ディレクティブの使用

次の例では、競合状態を回避できます (同時に更新する要素の*x*複数のスレッドによって) を使用して、`atomic`ディレクティブ ([セクション 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) [19] ページ)。

```
#pragma omp parallel for shared(x, y, index, n)
    for (i=0; i<n; i++)
    {
        #pragma omp atomic
            x[index[i]] += work1(i);
        y[i] += work2(i);
    }
```

使用する利点、`atomic`ディレクティブがこの例では、並列的に実行する x の 2 つの異なる要素の更新できます。 場合、`critical`ディレクティブ ([セクション 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) 18 ページ) の要素をすべてを更新し、代わりに、使用された*x*は逐次的に (ただし、順序は保証ではなく) 実行されます。

なお、`atomic`ディレクティブが、C または C++ ステートメントの直後にのみ適用されます。  その結果、要素の*y*この例ではアトミックに更新されません。