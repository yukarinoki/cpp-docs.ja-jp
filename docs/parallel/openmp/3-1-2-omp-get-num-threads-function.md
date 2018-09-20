---
title: 3.1.2 omp_get_num_threads 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: bcdd76e2-d96b-4884-ac8f-e55fc0c42801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 512c09b0cf71a7fd9c7438b6f9cceb9f16126718
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424985"
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