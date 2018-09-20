---
title: A.19 例 work-sharing ディレクティブの正しくない入れ子 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 906e900d-9259-44d6-a095-c1ba9135d269
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cf9502fd17fced7a4bc2a208634b825443f196a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411522"
---
# <a name="a19---examples-showing-incorrect-nesting-of-work-sharing-directives"></a>A.19 Work-sharing ディレクティブの正しくない入れ子の例

このセクションの例では、ディレクティブの入れ子の規則を説明します。 ディレクティブの入れ子の詳細については、次を参照してください。[セクション 2.9](../../parallel/openmp/2-9-directive-nesting.md) 33 ページの。

次の例が準拠していないため、内側と外側`for`ディレクティブは入れ子になったし、同じバインド`parallel`ディレクティブ。

```
void wrong1(int n)
{
  #pragma omp parallel default(shared)
  {
      int i, j;
      #pragma omp for
      for (i=0; i<n; i++) {
          #pragma omp for
              for (j=0; j<n; j++)
                 work(i, j);
     }
   }
}
```

前の例の次の動的に入れ子になったバージョンに準拠していないもです。

```
void wrong2(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++)
        work1(i, n);
  }
}

void work1(int i, int n)
{
  int j;
  #pragma omp for
    for (j=0; j<n; j++)
      work2(i, j);
}
```

次の例が準拠していないため、`for`と`single`ディレクティブは入れ子になっているし、同じ並列領域にバインドします。

```
void wrong3(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        #pragma omp single
          work(i);
      }
  }
}
```

次の例が準拠していないため、`barrier`ディレクティブ内で、`for`デッドロックが発生することができます。

```
void wrong4(int n)
{
  #pragma omp parallel default(shared)
  {
    int i;
    #pragma omp for
      for (i=0; i<n; i++) {
        work1(i);
        #pragma omp barrier
        work2(i);
      }
  }
}
```

次の例が準拠していないため、`barrier`デッドロック、一度に 1 つのスレッドがクリティカル セクションに入力できるという事実が原因になります。

```
void wrong5()
{
  #pragma omp parallel
  {
    #pragma omp critical
    {
       work1();
       #pragma omp barrier
       work2();
    }
  }
}
```

次の例が準拠していないため、 `barrier` 1 つのスレッドが実行されるという事実のデッドロックの結果、`single`セクション。

```
void wrong6()
{
  #pragma omp parallel
  {
    setup();
    #pragma omp single
    {
      work1();
      #pragma omp barrier
      work2();
    }
    finish();
  }
}
```