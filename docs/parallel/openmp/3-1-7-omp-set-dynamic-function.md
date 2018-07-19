---
title: 3.1.7 omp_set_dynamic 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 1fba961b-b82c-4a1e-ab0f-e4be826e50ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d1e22a1eb9aff32bfaf07350daf1cb397e18eb3
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687869"
---
# <a name="317-ompsetdynamic-function"></a>3.1.7 omp_set_dynamic 関数
**Omp_set_dynamic**関数を有効または並列領域を実行するために使用できるスレッドの数が動的に調整を無効にします。 形式は次のとおりです。  
  
```  
#include <omp.h>  
void omp_set_dynamic(int dynamic_threads);  
```  
  
 場合*dynamic_threads*評価 0 以外の値に後続の並列領域の実行に使用されるスレッドの数調整することが自動的にシステム リソースを最大限に活用する実行時環境でします。 結果として、ユーザーによって指定されたスレッドの数は、スレッドの最大数です。 並列領域を実行する、チーム内のスレッドの数がその並列領域の間で固定されたままし、によって報告された、 **omp_get_num_threads**関数。  
  
 場合*dynamic_threads*評価を 0 に動的に調整が無効になっています。  
  
 この関数は、プログラムの部分から呼び出されたときに、上記の効果を場所、 **omp_in_parallel**関数は 0 を返します。 プログラムの部分から呼び出されたかどうかはここで、 **omp_in_parallel**関数には、0 以外の値が返されます、この関数の動作は未定義です。  
  
 呼び出し**omp_set_dynamic**経由での優先順位を持つ、 **OMP_DYNAMIC**環境変数。  
  
 動的に調整するスレッドの既定値は、実装定義です。 その結果、スレッドの適切な実行の特定の数に依存しているユーザー コードは、明示的に動的スレッドを無効にする必要があります。 実装は、スレッドの数が動的に調整する機能を提供する必要はありませんが、すべてのプラットフォームでの移植性をサポートするために、インターフェイスを提供する必要があります。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **omp_get_num_threads**関数を参照してください[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) [37] ページ。  
  
-   **OMP_DYNAMIC**環境変数を参照してください[セクション 4.3](../../parallel/openmp/4-3-omp-dynamic.md) 49 ページにします。  
  
-   **omp_in_parallel**関数を参照してください[セクション 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md)ページ 38 です。