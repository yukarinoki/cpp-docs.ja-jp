---
title: E. OpenMP C と C++ での動作の実装で定義された |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b8d660ca-9bb3-4b6b-87af-45c67d43a731
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6e2e8360dbb2c8851a0ac1c09767928703708a97
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405009"
---
# <a name="e-implementation-defined-behaviors-in-openmp-cc"></a>E. OpenMP C/C の実装で定義された動作

この付録では、「実装で定義されている」この api として記述されている動作をまとめたものです。  各動作は、メインの仕様では、その説明に相互参照します。

## <a name="remarks"></a>Remarks

実装が定義し、このような場合は、その動作を文書化するために必要には、この一覧は完全でない可能性があります。

- **スレッドの数:** スレッドの数を動的に調整が無効になっているし、並列領域に対して要求されたスレッドの数は、実行時のシステムを提供できる、動作の数を超えています中に、並行領域が発生した場合。プログラムは、実装定義 (9 ページを参照してください)。

     Visual C で入れ子になっていない並列領域の 64 個のスレッド (最大) が提供されます。

- **プロセッサの数:** 実際には、特定の時点でスレッドをホストしている物理プロセッサの数は、実装で定義されている (10 ページを参照してください)。

     Visual C では、この数は、定数ではなくされ、オペレーティング システムによって制御されます。

- **スレッドのチームを作る:** チーム内の入れ子になった並列領域を実行するスレッドの数は、実装定義です (。10 ページを参照)。

     Visual c は、これは、オペレーティング システムによって決定されます。

- **schedule (runtime):** 実行時まで遅延に関するスケジュールが決定します。 スケジュールの種類とチャンクのサイズを設定して実行時に選択できます、`OMP_SCHEDULE`環境変数。 この環境変数が設定されていない場合、結果として得られるスケジュールは、実装定義 (13 ページを参照してください)。

     スケジュールの種類は、Visual C で`static`チャンク サイズがありません。

- **既定のスケジュール:** スケジュール句のない場合は、既定のスケジュールは、実装定義 (13 ページを参照してください)。

     既定のスケジュールの種類は、Visual C で`static`チャンク サイズがありません。

- **ATOMIC:** は実装で定義された実装がすべてを置換するかどうか`atomic`ディレクティブを**重要な**ディレクティブを持つ同じ一意の名前 (20 ページを参照してください)。

     によってデータが変更された場合、Visual C で[アトミック](../../parallel/openmp/reference/atomic.md)自然なアラインメント上にないか、そのプロパティを満たすすべての時間の長いのアトミック操作が 1 つの重要なセクションを使用して 1 つまたは 2 バイトである場合。 それ以外の場合、重要なセクションでは使用されません。

- **omp_get_num_threads:** スレッドの数が明示的に設定していない場合、ユーザーが、既定値は実装定義 (9 ページを参照してくださいと[セクション 3.1.2](../../parallel/openmp/3-1-2-omp-get-num-threads-function.md) [37] ページ)。

     Visual c は、既定のスレッド数がプロセッサの数と等しくします。

- **omp_set_dynamic:** 動的なスレッドの調整の既定値は実装定義 (を参照してください[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページ上)。

     既定では、Visual C で`FALSE`します。

- **omp_set_nested:** 実装で定義された入れ子になった並列領域の実行に使用されるスレッドの数は、入れ子になった並列処理が有効にすると (を参照してください[セクション 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) 40 ページ上)。

     Visual C では、スレッドの数をオペレーティング システムによって決まります。

- `OMP_SCHEDULE` 環境変数: この環境変数の既定値は実装定義 (を参照してください[セクション 4.1](../../parallel/openmp/4-1-omp-schedule.md) 48 ページ)。

     スケジュールの種類は、Visual C で`static`チャンク サイズがありません。

- `OMP_NUM_THREADS` 環境変数: の値が指定されていない場合、`OMP_NUM_THREADS`環境変数、または指定された値が正の整数または使用するスレッドの数は、値が、システムでサポートできるスレッドの最大数よりも大きい場合は、実装で定義された (を参照してください[セクション 4.2](../../parallel/openmp/4-2-omp-num-threads.md) 48 ページ)。

     Visual C でがゼロの値が指定されている場合または、以下の場合、スレッドの数がプロセッサの数と等しい。  値が 64 より大きい場合は、スレッドの数は 64 です。

- `OMP_DYNAMIC` 環境変数: 既定値は実装定義 (を参照してください[セクション 4.3](../../parallel/openmp/4-3-omp-dynamic.md) [49] ページ)。

     既定では、Visual C で`FALSE`します。