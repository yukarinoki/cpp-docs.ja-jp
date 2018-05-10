---
title: 4.2 OMP_NUM_THREADS |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6b4208d7fe7d453dd1f701d820a85fce5cd68ba
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS
**OMP_NUM_THREADS**環境変数がその番号が明示的に呼び出すことによって変更されない限り、既定の実行中に、使用するスレッド数を設定、 **omp_set_num_threads**ライブラリ ルーチンまたは明示的な**num_threads**句、**並列**ディレクティブです。  
  
 値、 **OMP_NUM_THREADS**環境変数は、正の整数を指定する必要があります。 その効果は、スレッドの数を動的に調整が有効になっているかどうかによって異なります。 間の相互作用についてのルールの包括的セット、 **OMP_NUM_THREADS**環境、スレッドの変数および動的な調整は、8 ページのセクションで 2.3 を参照してください。  
  
 値が指定されていない場合、 **OMP_NUM_THREADS**環境変数、または指定された値が正の整数ではないか、システムができる値がスレッドの最大数よりも大きい場合のサポートを使用するスレッドの数実装定義されます。  
  
 例:  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **num_threads**句を参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。  
  
-   **omp_set_num_threads**関数を参照してください[セクション 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md)ページ 36 にします。  
  
-   **omp_set_dynamic**関数を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md)ページ 39 にします。