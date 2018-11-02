---
title: A.11 固定数のスレッドの指定
ms.date: 11/04/2016
ms.assetid: 1d06b142-4c35-44b8-994b-20f2aed5462b
ms.openlocfilehash: 832afac9abc7edd03d3af6f567657aefd596aae0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492044"
---
# <a name="a11---specifying-a-fixed-number-of-threads"></a>A.11 固定数のスレッドの指定

一部のプログラムは正常に実行するスレッドの固定、事前の数に依存します。  スレッドの数を動的に調整の既定の設定は、実装定義であるために、このようなプログラムは、動的なスレッドの機能をオフにして、移植性を保証するには、明示的にスレッドの数を設定を選択できます。 次の例を使用してこれを行う方法を示しています。 `omp_set_dynamic` ([セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページで)、および`omp_set_num_threads`([セクション 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 ページ)。

```
omp_set_dynamic(0);
omp_set_num_threads(16);
#pragma omp parallel shared(x, npoints) private(iam, ipoints)
{
    if (omp_get_num_threads() != 16)
      abort();
    iam = omp_get_thread_num();
    ipoints = npoints/16;
    do_by_16(x, iam, ipoints);
}
```

プログラムは、この例では 16 のスレッドによって実行される場合にのみ正しく実行します。 実装が 16 のスレッドをサポートできない場合は、この例の動作は実装定義です。

動的なスレッドの設定に関係なく、並行領域の中に、並行領域を実行しているスレッドの数が一定に注意してください。 動的なスレッド メカニズムでは、並列領域の開始時に使用するスレッドの数を決定し、リージョンの間維持します。