---
title: A.15 使用されるスレッド数の確認
ms.date: 11/04/2016
ms.assetid: 026bb59a-f668-40db-a7cb-69a1bae83d2d
ms.openlocfilehash: bd5e897eeab35ec73c061d2ae02a4b85772e1255
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525836"
---
# <a name="a15---determining-the-number-of-threads-used"></a>A.15 使用されるスレッド数の確認

次の正しくない例を検討してください (の[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) [37] ページ)。

```
np = omp_get_num_threads(); // misplaced
#pragma omp parallel for schedule(static)
    for (i=0; i<np; i++)
        work(i);
```

`omp_get_num_threads()`ためシリアル、コードのセクションでは 1 を返しますを呼び出す*np*常に前の例を 1 に等しくなります。 並列領域に配置されるスレッドの数を調べるには、並行領域内の呼び出しでなければなりません。

次の例では、スレッドの数のクエリを含めずにこのプログラムを書き換える方法を示します。

```
#pragma omp parallel private(i)
{
    i = omp_get_thread_num();
    work(i);
}
```