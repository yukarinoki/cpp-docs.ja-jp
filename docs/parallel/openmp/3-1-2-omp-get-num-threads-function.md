---
title: 3.1.2 omp_get_num_threads 関数
ms.date: 11/04/2016
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
ms.openlocfilehash: 587b49f70896bcfe8c1a805a4ebb13a11e9bb7d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465248"
---
# <a name="312-ompgetnumthreads-function"></a>3.1.2 omp_get_num_threads 関数

**Omp_get_num_threads**関数の数を返しますスレッド現在、チームが並列に呼び出し元のリージョンを実行します。 形式は次のとおりです。

```
#include <omp.h>
int omp_get_num_threads(void);
```

**Num_threads**句、 **omp_set_num_threads**関数、および**OMP_NUM_THREADS**環境変数は、チーム内のスレッドの数を制御します。

スレッドの数が明示的に設定していない場合、ユーザーが、既定では実装定義です。 この関数に最も近い外側バインド**並列**ディレクティブ。 シリアル、プログラムの一部から、またはシリアル化される入れ子になった並列領域から呼び出されると、この関数は 1 を返します。

## <a name="cross-references"></a>クロス リファレンス

- **OMP_NUM_THREADS**環境変数を参照してください[セクション 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48 ページ。

- **num_threads**句を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの。

- **並列**構築を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの。