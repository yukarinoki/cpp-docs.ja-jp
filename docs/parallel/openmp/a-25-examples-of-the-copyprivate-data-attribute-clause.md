---
title: A.25 copyprivate データ属性句の例 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7b1cb6a5-5691-4b95-b3ac-d7543ede6405
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95d68c445c1c20e97725d869061027a9712c2462
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413642"
---
# <a name="a25---examples-of-the-copyprivate-data-attribute-clause"></a>A.25 copyprivate データ属性句の例

**例 1:** 、`copyprivate`句 ([セクション 2.7.2.8](../../parallel/openmp/2-7-2-8-copyprivate.md) [32] ページ)、他のスレッド内のプライベート変数のすべてのインスタンスに直接 1 つのスレッドによって取得された値をブロードキャストするために使用できます。

```
float x, y;
#pragma omp threadprivate(x, y)

void init( )
{
    float a;
    float b;

    #pragma omp single copyprivate(a,b,x,y)
    {
        get_values(a,b,x,y);
    }

    use_values(a, b, x, y);
}
```

ルーチン*init*というはシリアル領域から、その動作は、ディレクティブの存在することによって影響されませんが。 呼び出した後、 *get_values*ルーチンが 1 つのスレッドによって実行された、スレッドで指定されたプライベート オブジェクトまで、コンストラクトがない *、*、 *b*、 *x*、および*y*すべてのスレッドで読み取られた値で定義になります。

**例 2:** 前の例とは対照的には、マスター スレッドと、特定のスレッドによって、読み取りを実行する必要がありますとします。 ここで、`copyprivate`ブロードキャストを直接実行する句を使用することはできませんが、一時的な共有オブジェクトへのアクセスを提供するために使用できます。

```
float read_next( )
{
    float * tmp;
    float return_val;

    #pragma omp single copyprivate(tmp)
    {
        tmp = (float *) malloc(sizeof(float));
    }

    #pragma omp master
    {
        get_float( tmp );
    }

    #pragma omp barrier
    return_val = *tmp;
    #pragma omp barrier

    #pragma omp single
    {
       free(tmp);
    }

    return return_val;
}
```

**例 3:** 並行領域内で必要なロック オブジェクトの数はそれを入力する前に簡単に特定できないとします。 `copyprivate`その並行領域内で割り当てられている共有ロック オブジェクトへのアクセスを提供する句を使用できます。

```
#include <omp.h>

omp_lock_t *new_lock()
{
    omp_lock_t *lock_ptr;

    #pragma omp single copyprivate(lock_ptr)
    {
        lock_ptr = (omp_lock_t *) malloc(sizeof(omp_lock_t));
        omp_init_lock( lock_ptr );
    }

    return lock_ptr;
}
```