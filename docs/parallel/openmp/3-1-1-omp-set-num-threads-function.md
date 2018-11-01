---
title: 3.1.1 omp_set_num_threads 関数
ms.date: 11/04/2016
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
ms.openlocfilehash: 20b6b6ced2b4031696f1d019604842ae9b91bda2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663282"
---
# <a name="311-ompsetnumthreads-function"></a>3.1.1 omp_set_num_threads 関数

`omp_set_num_threads`関数が指定されていない後続の並列領域で使用するスレッド数の既定の設定、`num_threads`句。 形式は次のとおりです。

```
#include <omp.h>
void omp_set_num_threads(int num_threads);
```

パラメーターの値*num_threads*正の整数を指定する必要があります。 その効果は、スレッドの数を動的に調整が有効になっているかどうかによって異なります。 包括的な一連のルール間の相互作用についての`omp_set_num_threads`関数とスレッド、動的に調整セクション 2.3 を 8 ページを参照してください。

この関数は、プログラムの部分から呼び出されたときに上記で説明した効果を`omp_in_parallel`関数は 0 を返します。 プログラムの部分から呼び出されたかどうか、`omp_in_parallel`関数は 0 以外の値を返します、この関数の動作は未定義です。

この呼び出しに優先、`OMP_NUM_THREADS`環境変数。 スレッドである可能性がありますが呼び出すことで確立されている数の既定値`omp_set_num_threads`かを設定して、`OMP_NUM_THREADS`環境変数は、1 つで明示的にオーバーライド**並列**ディレクティブを指定して、`num_threads`句。

## <a name="cross-references"></a>クロス リファレンス

- `omp_set_dynamic` 関数を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページ。

- `omp_get_dynamic` 関数を参照してください[セクション 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) 40 ページの。

- `OMP_NUM_THREADS` 環境変数を参照してください[セクション 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 、48 ページと 8 ページのセクションでします。

- `num_threads` 句を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの