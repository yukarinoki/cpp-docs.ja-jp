---
title: OpenMP 環境変数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 2178ce2b-ffa1-45ec-a455-64437711d15d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02248b7725f2a4312f26984c798e7248463d2615
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="openmp-environment-variables"></a>OpenMP の環境変数
OpenMP API で使用される環境変数へのリンクを提供します。  
  
 OpenMP の標準の Visual C の実装には、次の環境変数が含まれています。 これらの環境変数がプログラムの起動時に読み取られ、実行時にその値への変更は無視されます (たとえばを使用して[_putenv、_wputenv](../../../c-runtime-library/reference/putenv-wputenv.md))。  
  
|環境変数|説明|  
|--------------------------|-----------------|  
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|OpenMP ランタイムが、並行領域内のスレッドの数を調整できるかどうかを指定します。|  
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|入れ子になった並列処理が有効かどう、入れ子になった並列処理が有効か無効にしない限り、指定`omp_set_nested`です。|  
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|オーバーライドされない限り、並行領域内のスレッドの最大数を設定[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)または[num_threads](../../../parallel/openmp/reference/num-threads.md)です。|  
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|動作を変更して、[スケジュール](../../../parallel/openmp/reference/schedule.md)句と`schedule(runtime)`で指定された、`for`または`parallel for`ディレクティブです。|  
  
## <a name="see-also"></a>関連項目  
 [ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)