---
title: A.17 入れ子にできるロックの使用
ms.date: 11/04/2016
ms.assetid: 8ef386ed-ddc4-4d40-80aa-cc39f0fb5e4b
ms.openlocfilehash: 769285bc0831d8968490b698d6fd9f96ff8d517f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579664"
---
# <a name="a17---using-nestable-locks"></a>A.17 入れ子にできるロックの使用

次の例では、(の[セクション 3.2](../../parallel/openmp/3-2-lock-functions.md) 41 ページの) 構造体全体とそのメンバーのいずれかの両方の更新を同期する入れ子にできるロックの使用方法を示します。

```
#include <omp.h>
typedef struct {int a,b; omp_nest_lock_t lck;} pair;

void incr_a(pair *p, int a)
{
    // Called only from incr_pair, no need to lock.
    p->a += a;
}

void incr_b(pair *p, int b)
{
    // Called both from incr_pair and elsewhere,
    // so need a nestable lock.

    omp_set_nest_lock(&p->lck);
    p->b += b;
    omp_unset_nest_lock(&p->lck);
}

void incr_pair(pair *p, int a, int b)
{
    omp_set_nest_lock(&p->lck);
    incr_a(p, a);
    incr_b(p, b);
    omp_unset_nest_lock(&p->lck);
}

void f(pair *p)
{
    extern int work1(), work2(), work3();
    #pragma omp parallel sections
    {
        #pragma omp section
            incr_pair(p, work1(), work2());
        #pragma omp section
            incr_b(p, work3());
    }
}
```