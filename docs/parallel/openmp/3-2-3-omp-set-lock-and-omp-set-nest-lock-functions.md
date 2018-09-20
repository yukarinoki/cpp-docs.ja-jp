---
title: 3.2.3 omp_set_lock 関数と omp_set_nest_lock 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b5323879-f72e-418e-953f-3979fdda17a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 792b95baef2821bb693d9a90fc228d2b0c508e1f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420362"
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