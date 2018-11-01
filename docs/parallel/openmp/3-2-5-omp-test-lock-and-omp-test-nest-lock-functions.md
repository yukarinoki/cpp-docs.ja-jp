---
title: 3.2.5 omp_test_lock 関数と omp_test_nest_lock 関数
ms.date: 11/04/2016
ms.assetid: 36818945-c22c-4c24-b754-4e73eba6f3f8
ms.openlocfilehash: e8e03699f807f23f139075560592d8846467f2c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512752"
---
# <a name="325-omptestlock-and-omptestnestlock-functions"></a>3.2.5 omp_test_lock 関数と omp_test_nest_lock 関数

これらの関数は、ロックを設定しようとしていますが、スレッドの実行はブロックしません。 形式は次のとおりです。

```
#include <omp.h>
int omp_test_lock(omp_lock_t *lock);
int omp_test_nest_lock(omp_nest_lock_t *lock);
```

引数は、ロックが初期化された変数をポイントする必要があります。 これらの関数と同様に、ロックを設定しようとしました。`omp_set_lock`と`omp_set_nest_lock`スレッドの実行をブロックしないことを除いて、します。

単純なロックを`omp_test_lock`関数が正常にロックが設定されている場合、0 以外の値を返します。 それ以外の場合、0 を返します。

入れ子にできるロックで、`omp_test_nest_lock`関数が正常にロックが設定されている場合、新しい入れ子数を返します。 それ以外の場合、0 を返します。