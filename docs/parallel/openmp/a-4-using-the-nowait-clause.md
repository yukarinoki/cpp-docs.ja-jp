---
title: A.4 nowait 句の使用
ms.date: 11/04/2016
ms.assetid: d3de2111-05ea-4ee3-a66c-57bd988712af
ms.openlocfilehash: 7f839397787c35e88ea325c2db81b15b3a4e7508
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454926"
---
# <a name="a4---using-the-nowait-clause"></a>A.4 nowait 句の使用

並行領域内で複数の独立したループがある場合は、使用、`nowait`句 ([セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) 11 ページの) の末尾にある暗黙のバリアを回避するために、`for`ディレクティブを次のとおりです。

```
#pragma omp parallel
{
    #pragma omp for nowait
        for (i=1; i<n; i++)
             b[i] = (a[i] + a[i-1]) / 2.0;
    #pragma omp for nowait
        for (i=0; i<m; i++)
            y[i] = sqrt(z[i]);
}
```