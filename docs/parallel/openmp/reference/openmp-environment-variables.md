---
title: OpenMP 環境変数 |Microsoft Docs
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
ms.openlocfilehash: 98b61535fd07066c4a1ee24658fdfe81047efc90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446570"
---
# <a name="openmp-environment-variables"></a>OpenMP の環境変数

OpenMP API で使用される環境変数へのリンクを提供します。

OpenMP の標準の Visual C の実装には、次の環境変数が含まれています。 これらの環境変数がプログラムの起動時に読み取られ、実行時にその値に対する変更は無視されます (たとえばを使用して[_putenv、_wputenv](../../../c-runtime-library/reference/putenv-wputenv.md))。

|環境変数|説明|
|--------------------------|-----------------|
|[OMP_DYNAMIC](../../../parallel/openmp/reference/omp-dynamic.md)|OpenMP の実行時に、並行領域内のスレッドの数を調整できるかどうかを指定します。|
|[OMP_NESTED](../../../parallel/openmp/reference/omp-nested.md)|入れ子になった並列処理が有効になってこと、入れ子になった並列処理を有効になっているかを無効になっている場合を除き、かどうかを指定します。`omp_set_nested`します。|
|[OMP_NUM_THREADS](../../../parallel/openmp/reference/omp-num-threads.md)|によってオーバーライドされない限り、並列の領域でスレッドの最大数を設定[omp_set_num_threads](../../../parallel/openmp/reference/omp-set-num-threads.md)または[num_threads](../../../parallel/openmp/reference/num-threads.md)します。|
|[OMP_SCHEDULE](../../../parallel/openmp/reference/omp-schedule.md)|動作を変更、[スケジュール](../../../parallel/openmp/reference/schedule.md)句と`schedule(runtime)`で指定された、`for`または`parallel for`ディレクティブ。|

## <a name="see-also"></a>関連項目

[ライブラリ リファレンス](../../../parallel/openmp/reference/openmp-library-reference.md)