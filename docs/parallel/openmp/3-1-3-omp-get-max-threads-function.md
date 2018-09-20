---
title: 3.1.3 omp_get_max_threads 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5548897c-546e-4d19-b37b-a76f6b30a0a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c439dc0203fa3435c62e9669da40b5b092556492
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400823"
---
# <a name="313-ompgetmaxthreads-function"></a>3.1.3 omp_get_max_threads 関数

**Omp_get_max_threads**チームを作ることがなく、並行領域の場合に使用されるスレッドの数とサイズ以上であることが保証される整数を返す、 **num_threads**句その時点でのコードを検出することでした。 形式は次のとおりです。

```
#include <omp.h>
int omp_get_max_threads(void);
```

次の値の下限の境界を表現する**omp_get_max_threads**:

```

threads-used-for-next-team
<= omp_get_max_threads

```

後続の並列地域で使用する場合、 **num_threads**句の結果の下限の境界上の保証、スレッドの特定の番号を要求する**omp_get_max_threads**ありません時間保持されます。

**Omp_get_max_threads**関数の戻り値は、後続の並列領域で形成されるチームのすべてのスレッドに十分な記憶域を動的に割り当てるには使用できます。

## <a name="cross-references"></a>クロス リファレンス

- **omp_get_num_threads**関数を参照してください[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 ページ。

- **omp_set_num_threads**関数を参照してください[セクション 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 ページ。

- **omp_set_dynamic**関数を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページ。

- **num_threads**句を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの。