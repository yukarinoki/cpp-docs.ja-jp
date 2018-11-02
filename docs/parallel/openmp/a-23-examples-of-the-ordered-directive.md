---
title: A.23 ordered ディレクティブの例
ms.date: 11/04/2016
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
ms.openlocfilehash: 2868b771fd57613981f3c6458b48493a1b26eee4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50472280"
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23 ordered ディレクティブの例

複数の順序付けられたセクションをすることができます、`for`で指定された、`ordered`句。 API は、次を指定するため、最初の例が準拠していません。

"使用して、ループのイテレーションを`for`コンストラクトでは同じ実行する必要がありますされません`ordered`ディレクティブを超えると、その 1 つ以上実行する必要がありますいない`ordered`ディレクティブ"。 (を参照してください[セクション 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) 22 ページ)

この規則違反の例では、すべてのイテレーションは、2 つの順序付けられたセクションを実行します。

```
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    #pragma omp ordered
    { ... }
    ...
    #pragma omp ordered
    { ... }
    ...
}
```

準拠している例を次に示します、`for`順序付けられた複数のセクション。

```
#pragma omp for ordered
for (i=0; i<n; i++)
{
    ...
    if (i <= 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
    (i > 10)
    {
        ...
        #pragma omp ordered
        { ... }
    }
    ...
}
```