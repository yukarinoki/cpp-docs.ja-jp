---
description: 詳細については、「OpenMP から同時実行ランタイムへの移行」を参照してください。
title: OpenMP からコンカレンシー ランタイムへの移行
ms.date: 11/04/2016
helpviewer_keywords:
- Concurrency Runtime, migrating from OpenMP
- OpenMP, migrating to the Concurrency Runtime
ms.assetid: 9bab7bb1-e45d-44b2-8509-3b226be2c93b
ms.openlocfilehash: ab9b50f0cdebcc8fc601565dd19c5c2704c17d95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193085"
---
# <a name="migrating-from-openmp-to-the-concurrency-runtime"></a>OpenMP からコンカレンシー ランタイムへの移行

コンカレンシー ランタイムでは、さまざまなプログラミング モデルを使用できます。 これらのモデルは、他のライブラリのモデルと重複する場合や、他のライブラリのモデルを補完する場合があります。 このセクションのドキュメントでは、 [openmp](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp) と同時実行ランタイムを比較し、既存の openmp コードを移行して同時実行ランタイムを使用する方法の例を示します。

OpenMP プログラミング モデルは、オープン標準により定義されており、Fortran および C/C++ プログラミング言語へのバインドが適切に定義されています。 Microsoft C++ コンパイラでサポートされている OpenMP バージョン2.0 および2.5 は、反復的な並列アルゴリズムに適しています。つまり、データの配列に対して並列反復処理を実行します。 OpenMP 3.0 では、反復的なタスクに加えて反復的ではないタスクがサポートされています。

OpenMP は、並列化の度合いが事前に決定され、システムで使用可能なリソースと対応する場合に最も効果的です。 OpenMP モデルは、非常に大規模な計算の問題が1台のコンピューターの処理リソース全体に分散されるハイパフォーマンスコンピューティングに特に適しています。 このシナリオでは、通常、ハードウェア環境は固定されており、開発者は、アルゴリズムの実行時にすべてのコンピューティングリソースに排他的にアクセスすることを想定できます。

ただし、制約の少ないコンピューティング環境は、OpenMP に適しているとは限りません。 たとえば、再帰的な問題 (クイックソートアルゴリズム、データツリーの検索など) は、OpenMP 2.0 および2.5 を使用して実装するのが困難です。 同時実行ランタイムは、 [非同期エージェントライブラリ](../../parallel/concrt/asynchronous-agents-library.md) と [並列パターンライブラリ](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) を提供することによって、OpenMP の機能を補完します。 非同期エージェントライブラリでは、粒度の粗いタスク並列処理がサポートされています。PPL では、よりきめ細かな並列タスクがサポートされています。 同時実行ランタイムには、アプリケーションのロジックに集中できるように、操作を並列で実行するために必要なインフラストラクチャが用意されています。 ただし、同時実行ランタイムによってさまざまなプログラミングモデルが有効になるため、スケジュールのオーバーヘッドは、OpenMP などの他の同時実行ライブラリよりも大きくなる可能性があります。 したがって、既存の OpenMP コードを変換して同時実行ランタイムを使用する場合は、パフォーマンスを段階的にテストすることをお勧めします。

## <a name="when-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP から同時実行ランタイムに移行する場合

既存の OpenMP コードを移行して、次のような場合に同時実行ランタイムを使用すると便利な場合があります。

|ケース|同時実行ランタイムの利点|
|-----------|-------------------------------------------|
|拡張可能な同時実行プログラミングフレームワークが必要です。|コンカレンシー ランタイムの機能の多くは拡張できます。 既存の機能を組み合わせて新しい機能を作成することもできます。 OpenMP はコンパイラディレクティブに依存しているため、簡単に拡張することはできません。|
|アプリケーションでは、協調ブロッキングの恩恵を受けることができます。|まだ使用できないリソースを必要とするためにタスクがブロックされた場合、同時実行ランタイムは、最初のタスクがリソースを待機している間に他のタスクを実行できます。|
|アプリケーションでは、動的な負荷分散のメリットが得られます。|同時実行ランタイムは、ワークロードの変化に合わせてコンピューティングリソースの割り当てを調整するスケジューリングアルゴリズムを使用します。 OpenMP では、scheduler がコンピューティングリソースを並列リージョンに割り当てるときに、これらのリソース割り当ては計算全体で固定されます。|
|例外処理のサポートが必要です。|PPL を使用すると、並列領域やループの内部と外部の両方で例外をキャッチできます。 OpenMP では、並列領域またはループ内の例外を処理する必要があります。|
|キャンセルメカニズムが必要です。|PPL を使用すると、アプリケーションは個別のタスクと作業ツリーの両方を取り消すことができます。 OpenMP では、アプリケーションが独自のキャンセルメカニズムを実装する必要があります。|
|並列コードは、開始元とは異なるコンテキストで終了する必要があります。|同時実行ランタイムを使用すると、1つのコンテキストでタスクを開始し、そのタスクを別のコンテキストで待機または取り消すことができます。 OpenMP では、すべての並列処理は、開始元のコンテキストで終了する必要があります。|
|デバッグのサポートを強化する必要があります。|Visual Studio には、[ **並列スタック** ] ウィンドウと [ **並列タスク** ] ウィンドウが用意されているため、マルチスレッドアプリケーションをより簡単にデバッグできます。<br /><br /> 同時実行ランタイムのデバッグサポートの詳細については、「[ [タスク] ウィンドウの使用](/visualstudio/debugger/using-the-tasks-window)」、「 [並列スタックの使用」](/visualstudio/debugger/using-the-parallel-stacks-window)、および「 [チュートリアル: 並列アプリケーションのデバッグ](/visualstudio/debugger/walkthrough-debugging-a-parallel-application)」を参照してください。|

## <a name="when-not-to-migrate-from-openmp-to-the-concurrency-runtime"></a>OpenMP から同時実行ランタイムに移行しない場合

次の例では、同時実行ランタイムを使用するために既存の OpenMP コードを移行することが適切でない場合について説明します。

|ケース|説明|
|-----------|-----------------|
|アプリケーションは既に要件を満たしています。|アプリケーションのパフォーマンスと現在のデバッグサポートに満足している場合は、移行が適切でない可能性があります。|
|並列ループ本体は、ほとんど処理を行いません。|同時実行ランタイムタスクスケジューラのオーバーヘッドにより、ループ本体を並列実行する利点 (特にループ本体が比較的小さい場合) が解決されない場合があります。|
|アプリケーションは C で記述されています。|同時実行ランタイムは多くの C++ 機能を使用するため、C アプリケーションで完全に使用できるコードを記述できない場合には適していない可能性があります。|

## <a name="related-topics"></a>関連トピック

[方法: OpenMP parallel for ループを変換して同時実行ランタイムを使用する](../../parallel/concrt/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime.md)

OpenMP [parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel) およびディレクティブ [を](../openmp/reference/openmp-directives.md#for-openmp) 使用する基本的なループを指定すると、同時実行ランタイム [Concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) アルゴリズムを使用するように変換する方法を示します。

[方法: キャンセルを使用する OpenMP ループを変換して同時実行ランタイムを使用する](../../parallel/concrt/convert-an-openmp-loop-that-uses-cancellation.md)<br/>
すべてのイテレーションの実行を必要としない OpenMP [parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp) ループが指定されている場合、同時実行ランタイムのキャンセルメカニズムを使用するように変換する方法を示します。

[方法: 例外処理を使用する OpenMP ループを変換して同時実行ランタイムを使用する](../../parallel/concrt/convert-an-openmp-loop-that-uses-exception-handling.md)<br/>
例外処理を実行する OpenMP [parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp) ループが指定されている場合、同時実行ランタイム例外処理機構を使用するように変換する方法を示します。

[方法: リダクション変数を使用する OpenMP ループを変換して同時実行ランタイムを使用する](../../parallel/concrt/convert-an-openmp-loop-that-uses-a-reduction-variable.md)<br/>
[リダクション](../openmp/reference/openmp-clauses.md#reduction)句を使用する OpenMP [parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp)ループが指定されている場合、その同時実行ランタイムを使用するように変換する方法を示します。

## <a name="see-also"></a>関連項目

[コンカレンシー ランタイム](../../parallel/concrt/concurrency-runtime.md)<br/>
[OpenMP](../../parallel/concrt/comparing-the-concurrency-runtime-to-other-concurrency-models.md#openmp)<br/>
[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)
