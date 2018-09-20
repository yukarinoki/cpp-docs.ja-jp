---
title: A.12 atomic ディレクティブの使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04daed582cfe87f6e4803b30919af3e07037de7f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378749"
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