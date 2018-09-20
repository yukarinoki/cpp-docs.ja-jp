---
title: 3.2.4 omp_unset_lock 関数と omp_unset_nest_lock 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5357e43e-a7c0-41d7-b529-3f7d15da8b11
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 426ac0a5ff974e486f70eed2965fdc27d5acc941
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419114"
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