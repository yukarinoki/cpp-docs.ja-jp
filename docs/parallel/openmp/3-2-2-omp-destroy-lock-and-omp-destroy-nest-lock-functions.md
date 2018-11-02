---
title: 3.2.2 omp_destroy_lock 関数と omp_destroy_nest_lock 関数
ms.date: 11/04/2016
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
ms.openlocfilehash: 02f739ab2834db7eca9b051e6659644c39b51e84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666204"
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock 関数と omp_destroy_nest_lock 関数

これらの関数いることを確認、指す変数のロックに*ロック*が初期化されていません。 形式は次のとおりです。

```
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

呼び出すには、ロック変数が初期化されていないか、ロックを解除するこれらのルーチンのいずれかの非準拠になります。