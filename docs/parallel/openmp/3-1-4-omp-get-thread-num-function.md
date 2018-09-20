---
title: 3.1.4 omp_get_thread_num 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5220402b-c109-4b1f-ba79-002e93d08617
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a21a682c051daffde16b3d5cfc63fd2d679c4de
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444919"
---
# <a name="314-ompgetthreadnum-function"></a>3.1.4 omp_get_thread_num 関数

`omp_get_thread_num`関数のスレッドの数を返します、のチーム内で関数を実行するスレッド。 スレッドの番号は 0 との間および**omp_get_num_threads()**-1、包括的です。 チームのマスター スレッドはスレッド 0 です。

形式は次のとおりです。

```
#include <omp.h>
int omp_get_thread_num(void);
```

シリアル領域から呼び出された場合`omp_get_thread_num`0 を返します。 シリアル化される入れ子になった並列領域内から呼び出されると、この関数は 0 を返します。

## <a name="cross-references"></a>クロス リファレンス

- `omp_get_num_threads` 関数を参照してください[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) 37 ページ。