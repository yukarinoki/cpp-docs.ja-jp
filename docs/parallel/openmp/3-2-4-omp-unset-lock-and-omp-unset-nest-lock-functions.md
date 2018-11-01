---
title: 3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数
ms.date: 11/04/2016
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
ms.openlocfilehash: b0764e3590f8edb3a3e783d9b5493a64be154401
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607867"
---
# <a name="324-ompunsetlock-and-ompunsetnestlock-functions"></a>3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数

これらの関数では、ロックの所有権を解放する手段を提供します。 形式は次のとおりです。

```
#include <omp.h>
void omp_unset_lock(omp_lock_t *lock);
void omp_unset_nest_lock(omp_nest_lock_t *lock);
```

これらの各関数の引数は、関数を実行するスレッドによって所有されているロックが初期化された変数をポイントする必要があります。 スレッドがそのロックを所有していない場合、動作は未定義です。

単純なロックを`omp_unset_lock`関数は、ロックの所有権から関数を実行するスレッドを解放します。

入れ子にできるロックで、`omp_unset_nest_lock`関数デクリメント、入れ子のカウントとリリース、結果のカウントが 0 の場合、ロックの所有権から関数を実行するスレッド。