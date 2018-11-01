---
title: 3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数
ms.date: 11/04/2016
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
ms.openlocfilehash: 8efc1f844be2d1b8cf9b15242758914edd0fca14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617660"
---
# <a name="323-ompsetlock-and-ompsetnestlock-functions"></a>3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数

これらの各関数は、指定されたロックがあるし、ロックを設定するまで、関数の実行スレッドをブロックします。 単純なロックでは、ロックされていない場合があります。 ロックされていない場合、または関数を実行するスレッドによって既に所有している場合は、入れ子にできるロックは使用します。 形式は次のとおりです。

```
#include <omp.h>
void omp_set_lock(omp_lock_t *lock);
void omp_set_nest_lock(omp_nest_lock_t *lock);
```

単純なロックを引数、`omp_set_lock`関数は、初期化されたロックの変数を指す必要があります。 ロックの所有権は、関数を実行しているスレッドに付与されます。

入れ子にできるロックでの引数、`omp_set_nest_lock`関数は、初期化されたロックの変数を指す必要があります。 入れ子のカウントをインクリメントし、スレッドが付与されるか、ロックの所有権を保持します。 します。