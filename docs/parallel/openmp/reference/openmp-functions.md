---
title: OpenMP 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: a55a2e5c-a260-44ee-bbd6-de7e2351b384
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a39fe44ff053a2e49a1067d0af071353e0a50ece
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693277"
---
# <a name="openmp-functions"></a>OpenMP の関数
OpenMP API で使用される関数へのリンクを提供します。  
  
 OpenMP の標準の Visual C の実装には、次の関数が含まれています。  
  
|関数|説明|  
|--------------|-----------------|  
|[omp_destroy_lock](../../../parallel/openmp/reference/omp-destroy-lock.md)|ロックの初期化を解除します。|  
|[omp_destroy_nest_lock](../../../parallel/openmp/reference/omp-destroy-nest-lock.md)|入れ子にできるロックの初期化を解除します。|  
|[omp_get_dynamic](../../../parallel/openmp/reference/omp-get-dynamic.md)|実行時以降の並列領域で使用できるスレッドの数を調整することができるかどうかを示す値を返します。|  
|[omp_get_max_threads](../../../parallel/openmp/reference/omp-get-max-threads.md)|並行領域なし場合、で利用できるスレッドの数を示す整数を返します[num_threads](../../../parallel/openmp/reference/num-threads.md)その時点で、コードで定義されました。|  
|[omp_get_nested](../../../parallel/openmp/reference/omp-get-nested.md)|入れ子になった並列処理が有効になっているかどうかを示す値を返します。|  
|[omp_get_num_procs](../../../parallel/openmp/reference/omp-get-num-procs.md)|関数が呼び出されたときに使用できるプロセッサの数を返します。|  
|[omp_get_num_threads](../../../parallel/openmp/reference/omp-get-num-threads.md)|並行領域内のスレッドの数を返します。|  
|[omp_get_thread_num](../../../parallel/openmp/reference/omp-get-thread-num.md)|そのスレッド チーム内で実行するスレッドのスレッド数を返します。|  
|[omp_get_wtick](../../../parallel/openmp/reference/omp-get-wtick.md)|プロセッサのクロックのティック間の秒数を返します。|  
|[omp_get_wtime](../../../parallel/openmp/reference/omp-get-wtime.md)|ある時点から経過した時間の秒の値を返します。|  
|[omp_in_parallel](../../../parallel/openmp/reference/omp-in-parallel.md)|並行領域内から呼び出された場合は 0 以外を返します。|  
|[omp_init_lock](../../../parallel/openmp/reference/omp-init-lock.md)|単純なロックを初期化します。|  
|[omp_init_nest_lock](../../../parallel/openmp/reference/omp-init-nest-lock.md)|ロックを初期化します。|  
|[omp_set_dynamic](../../../parallel/openmp/reference/omp-set-dynamic.md)|実行時以降の並列領域で使用できるスレッドの数を調整できることを示します。|  
|[omp_set_lock](../../../parallel/openmp/reference/omp-set-lock.md)|ロックが利用可能になるまで、スレッドの実行をブロックします。|  
|[omp_set_nest_lock](../../../parallel/openmp/reference/omp-set-nest-lock.md)|ロックが利用可能になるまで、スレッドの実行をブロックします。|  
|[omp_set_nested](../../../parallel/openmp/reference/omp-set-nested.md)|入れ子になった並列処理を有効にします。|  
|[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)|オーバーライドされない限り、後続の並列領域で、スレッドの数を設定、 [num_threads](../../../parallel/openmp/reference/num-threads.md)句。|  
|[omp_test_lock](../../../parallel/openmp/reference/omp-test-lock.md)|ロックを設定しようとしていますが、スレッドの実行をブロックしません。|  
|[omp_test_nest_lock](../../../parallel/openmp/reference/omp-test-nest-lock.md)|入れ子にできるロックを設定しようとしていますが、スレッドの実行をブロックしません。|  
|[omp_unset_lock](../../../parallel/openmp/reference/omp-unset-lock.md)|ロックを解放します。|  
|[omp_unset_nest_lock](../../../parallel/openmp/reference/omp-unset-nest-lock.md)|入れ子にできるロックを解放します。|  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)