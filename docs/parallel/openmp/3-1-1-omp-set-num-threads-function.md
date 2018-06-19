---
title: 3.1.1 omp_set_num_threads 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b94cf2b5-8011-4a3b-ba56-676982642857
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99c82ff324cbf21612d2459511877d152e2757f5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688441"
---
# <a name="311-ompsetnumthreads-function"></a>3.1.1 omp_set_num_threads 関数
`omp_set_num_threads`関数が指定されていない後続の並列領域で使用するスレッド数の既定の設定、`num_threads`句。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_set_num_threads(int num_threads);  
```  
  
 パラメーターの値*num_threads*正の整数を指定する必要があります。 その効果は、スレッドの数を動的に調整が有効になっているかどうかによって異なります。 間の相互作用についてのルールの包括的セット、`omp_set_num_threads`関数とスレッド、動的に調整 8 ページのセクションで 2.3 を参照してください。  
  
 この関数は、プログラムの部分から呼び出されたときに、上記の効果を場所、`omp_in_parallel`関数は 0 を返します。 プログラムの部分から呼び出されたかどうかはここで、`omp_in_parallel`関数には、0 以外の値が返されます、この関数の動作は未定義です。  
  
 この呼び出しに優先、`OMP_NUM_THREADS`環境変数。 呼び出すことによって確立された可能性がありますのスレッドの数の既定値`omp_set_num_threads`かを設定して、`OMP_NUM_THREADS`環境変数は、1 つに明示的にオーバーライドできます**並列**ディレクティブを指定することで、`num_threads`句。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   `omp_set_dynamic` 関数を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページ 39 にします。  
  
-   `omp_get_dynamic` 関数を参照してください[セクション 3.1.8](../../parallel/openmp/3-1-8-omp-get-dynamic-function.md) 40 ページのです。  
  
-   `OMP_NUM_THREADS` 環境変数を参照してください[セクション 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48、ページと 8 ページのセクション 2.3 にします。  
  
-   `num_threads` 句を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの