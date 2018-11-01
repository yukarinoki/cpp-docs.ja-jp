---
title: A.10 順番の指定
ms.date: 11/04/2016
ms.assetid: 5c65a9b1-0fc5-4cad-a5a9-9ce10b25d25c
ms.openlocfilehash: 4e3a146e1bca988f46cf7a7ee504644f96dab67e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575254"
---
# <a name="a10---specifying-sequential-ordering"></a>A.10 順番の指定

セクションの順序付け ([セクション 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) 22 ページ上) は並列で行われる作業からの出力を順番に配置するのに役立ちます。 次のプログラムは、順番にインデックスを印刷します。

```
#pragma omp for ordered schedule(dynamic)
    for (i=lb; i<ub; i+=st)
        work(i);
void work(int k)
{
    #pragma omp ordered
        printf_s(" %d", k);
}
```