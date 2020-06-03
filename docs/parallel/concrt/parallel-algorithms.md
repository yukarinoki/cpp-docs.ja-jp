---
title: 並列アルゴリズム
ms.date: 11/19/2018
helpviewer_keywords:
- parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
ms.openlocfilehash: a31787172c89e23e5eb32aa203b9f541584c0f68
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363204"
---
# <a name="parallel-algorithms"></a>並列アルゴリズム

並列パターン ライブラリ (PPL) は、データのコレクションに対して同時に処理を実行するアルゴリズムを提供します。 これらのアルゴリズムは、C++ 標準ライブラリで提供されるアルゴリズムに似ています。

並列アルゴリズムは、同時実行ランタイムの既存の機能から構成されます。 たとえば、[同時実行::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムでは、並列ループ反復処理を実行するために[同時実行::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)オブジェクトを使用します。 使用可能`parallel_for`なコンピューティング リソースの数が指定されている場合、アルゴリズム パーティションは最適な方法で動作します。

## <a name="sections"></a><a name="top"></a>セクション

- [parallel_for アルゴリズム](#parallel_for)

- [parallel_for_each アルゴリズム](#parallel_for_each)

- [parallel_invoke アルゴリズム](#parallel_invoke)

- [parallel_transform アルゴリズムと parallel_reduce アルゴリズム](#parallel_transform_reduce)

  - [parallel_transform アルゴリズム](#parallel_transform)

  - [parallel_reduce アルゴリズム](#parallel_reduce)

  - [例: マップと縮小を並行して実行する](#map_reduce_example)

- [パーティション分割作業](#partitions)

- [並列並べ替え](#parallel_sorting)

  - [並べ替えアルゴリズムを選択する](#choose_sort)

## <a name="the-parallel_for-algorithm"></a><a name="parallel_for"></a>parallel_forアルゴリズム

[同時実行::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムは、同じタスクを並列に繰り返し実行します。 これらのタスクは、それぞれ反復値でパラメーター化されます。 このアルゴリズムは、ループ本体がループの反復間でリソースを共有しない場合に便利です。

この`parallel_for`アルゴリズムは、並列実行に最適な方法でタスクを分割します。 ワークロードのバランスが崩れている場合は、ワーク・スチール・アルゴリズムと範囲の盗難を使用して、これらのパーティションのバランスを取ります。 ループの反復処理が協調的にブロックされると、ランタイムは、現在のスレッドに割り当てられている反復の範囲を他のスレッドまたはプロセッサに再配分します。 同様に、スレッドが一部の反復処理を完了すると、ランタイムは他のスレッドからそのスレッドに作業を再配分します。 この`parallel_for`アルゴリズムは *、ネストされた並列処理*もサポートしています。 1 つの並列ループに別の並列ループが含まれる場合、ランタイムはループ本体間の処理リソースを並列実行に効率的に調整します。

アルゴリズム`parallel_for`には、いくつかのオーバーロードされたバージョンがあります。 最初のバージョンは、開始値、終了値、および作業関数 (ラムダ式、関数オブジェクト、または関数ポインター) を受け取ります。 2 番目のバージョンは、開始値、終了値、ステップに使用する値、および作業関数を受け取ります。 この関数の最初のバージョンでは、ステップ値として 1 を使用します。 残りのバージョンはパーティショナー オブジェクトを使用するため、スレッド`parallel_for`間での範囲のパーティション分割方法を指定できます。 パーティショナについては、このドキュメントの「[パーティション分割](#partitions)作業」で詳しく説明します。

多くの`for`ループを変換して を`parallel_for`使用することができます。 ただし、この`parallel_for`アルゴリズムは、次の`for`点でステートメントと異なります。

- この`parallel_for`アルゴリズム`parallel_for`では、タスクは事前に決定された順序で実行されません。

- この`parallel_for`アルゴリズムは、任意の終了条件をサポートしていません。 `parallel_for`反復変数の現在の値が`last`1 より小さい場合、アルゴリズムは停止します。

- 型`_Index_type`パラメーターは整数型である必要があります。 この整数型は、符号付きまたは符号なしの場合があります。

- ループの反復は、順方向にする必要があります。 パラメーターが 1 未満の場合、アルゴリズムは[、std::invalid_argument](../../standard-library/invalid-argument-class.md)型の例外をスローします`_Step` `parallel_for`

- `parallel_for`アルゴリズムの例外処理メカニズムは`for`、ループの場合とは異なります。 並列ループ本体で複数の例外が同時に発生する場合、ランタイムは、 を呼び出した`parallel_for`スレッドに例外の 1 つだけを伝搬します。 さらに、1 つのループ反復が例外をスローしても、ランタイムはループ全体を直ちに停止しません。 代わりに、ループはキャンセルされた状態に置かれ、ランタイムはまだ開始されていないタスクを破棄します。 例外処理と並列アルゴリズムの詳細については、「[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)」を参照してください。

このアルゴリズム`parallel_for`では任意の終了条件はサポートされていませんが、キャンセルを使用してすべてのタスクを停止できます。 キャンセルの詳細については[、PPL のキャンセルを](cancellation-in-the-ppl.md)参照してください。

> [!NOTE]
> ロード バランシングとキャンセルなどの機能のサポートによって生じるスケジューリングコストは、ループ本体が比較的小さい場合に特に、ループ本体を並列に実行する利点を克服できない場合があります。 並列ループでパーティショナーを使用すると、このオーバーヘッドを最小限に抑えることができます。 詳細については、このドキュメント[の「パーティション分割作業](#partitions)」を参照してください。

### <a name="example"></a>例

次の例は、アルゴリズムの基本的な`parallel_for`構造を示しています。 この例では、範囲 [1, 5] の各値をコンソールに同時に出力します。

[!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
1 2 4 3 5
```

アルゴリズムは`parallel_for`各項目に対して並列に作用するため、値がコンソールに出力される順序は異なります。

`parallel_for`このアルゴリズムを使用する完全な例については、「[方法: parallel_for ループを作成する」を](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)参照してください。

[[トップ](#top)]

## <a name="the-parallel_for_each-algorithm"></a><a name="parallel_for_each"></a>parallel_for_eachアルゴリズム

[同時実行::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズムは、C++ 標準ライブラリで提供されるような反復コンテナー上でタスクを並列に実行します。 このアルゴリズムでは、`parallel_for` アルゴリズムで使用されるのと同じ分割ロジックが使用されます。

この`parallel_for_each`アルゴリズムは、C++ 標準ライブラリ[std::for_each](../../standard-library/algorithm-functions.md#for_each)アルゴリズムに似`parallel_for_each`ていますが、タスクが同時に実行される点が異なっています。 他の並列アルゴリズムと同様`parallel_for_each`に、特定の順序でタスクを実行しません。

このアルゴリズム`parallel_for_each`は、フォワード反復子とランダム アクセス反復子の両方で機能しますが、ランダム アクセス反復子の方が優れています。

### <a name="example"></a>例

次の例は、アルゴリズムの基本的な`parallel_for_each`構造を示しています。 この例では[、std::array](../../standard-library/array-class-stl.md)オブジェクトの各値をコンソールに並列で出力します。

[!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
4 5 1 2 3
```

アルゴリズムは`parallel_for_each`各項目に対して並列に作用するため、値がコンソールに出力される順序は異なります。

`parallel_for_each`このアルゴリズムを使用する完全な例については、「[方法: parallel_for_each ループを作成する](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)」を参照してください。

[[トップ](#top)]

## <a name="the-parallel_invoke-algorithm"></a><a name="parallel_invoke"></a>parallel_invokeアルゴリズム

[同時実行::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)アルゴリズムは、一連のタスクを並列で実行します。 各タスクが終了するまでは戻りません。 このアルゴリズムは、複数の独立したタスクを同時に実行する場合に便利です。

この`parallel_invoke`アルゴリズムは、そのパラメータとして一連の作業関数 (ラムダ関数、関数オブジェクト、または関数ポインタ) を受け取ります。 アルゴリズム`parallel_invoke`は、2 つから 10 個のパラメータを受け取るためにオーバーロードされます。 渡すすべての関数は、`parallel_invoke`ゼロのパラメーターを受け取る必要があります。

他の並列アルゴリズムと同様`parallel_invoke`に、特定の順序でタスクを実行しません。 トピック[「タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)」では`parallel_invoke`、アルゴリズムがタスクおよびタスク グループにどのように関連するかを説明しています。

### <a name="example"></a>例

次の例は、アルゴリズムの基本的な`parallel_invoke`構造を示しています。 この例では、3`twice`つのローカル変数で関数を同時に呼び出し、その結果をコンソールに出力します。

[!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
108 11.2 HelloHello
```

このアルゴリズムを使用する完全な例については、「[方法 : parallel_invokeを使用して並列ソートルーチンを作成する](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)」および「[方法 : parallel_invokeを使用して並列操作を実行する](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)」を参照してください。 `parallel_invoke`

[[トップ](#top)]

## <a name="the-parallel_transform-and-parallel_reduce-algorithms"></a><a name="parallel_transform_reduce"></a>parallel_transformとparallel_reduceアルゴリズム

[同時実行::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)と[同時実行::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)アルゴリズムは、それぞれ C++ 標準ライブラリ アルゴリズム[std::transform](../../standard-library/algorithm-functions.md#transform)と[std::累積](../../standard-library/numeric-functions.md#accumulate)の並列バージョンです。 同時実行ランタイムバージョンは、並列実行されるため、操作順序が決定されない点を除いて、C++ 標準ライブラリのバージョンと同様に動作します。 並列処理によってパフォーマンスとスケーラビリティの利点を得るために十分な大きさのセットを使用する場合は、これらのアルゴリズムを使用します。

> [!IMPORTANT]
> および`parallel_transform``parallel_reduce`アルゴリズムは、ランダム アクセス、双方向、および前方反復子のみをサポートします。 また、これらの反復子は、非`const`l 値を生成する必要があります。

### <a name="the-parallel_transform-algorithm"></a><a name="parallel_transform"></a>parallel_transformアルゴリズム

このアルゴリズムを`parallel transform`使用して、多くのデータ並列化操作を実行できます。 たとえば、次のように操作できます。

- 画像の明るさを調整し、その他の画像処理操作を行います。

- 2 つのベクトル間のドット積を合計または取り、ベクトルに対して他の数値計算を実行します。

- 3-D レイ トレースを実行し、各反復はレンダリングする必要がある 1 つのピクセルを参照します。

次の例は、アルゴリズムの呼び出しに使用`parallel_transform`される基本構造を示しています。 この例では、std::[vector](../../standard-library/vector-class.md)オブジェクトの各要素を 2 とおりの方法で否定します。 最初の方法では、ラムダ式を使用します。 2 番目の方法では[、std::negate](../../standard-library/negate-struct.md)を使用して[、std::unary_function](../../standard-library/unary-function-struct.md)から派生します。

[!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]

> [!WARNING]
> この例では、 の基本的な`parallel_transform`使用方法を示します。 この例では、作業関数は大幅な作業を行わないため、パフォーマンスの大幅な向上は期待できません。

アルゴリズム`parallel_transform`には 2 つのオーバーロードがあります。 最初のオーバーロードは、1 つの入力範囲と単項関数を使用します。 単項関数は、1 つの引数、関数オブジェクト、または から`unary_function`派生する型を受け取るラムダ式です。 2 番目のオーバーロードは、2 つの入力範囲と 2 進関数を受け取ります。 バイナリ関数は、2 つの引数、関数オブジェクト、または[std::binary_function](../../standard-library/binary-function-struct.md)から派生する型を受け取るラムダ式です。 次の例は、これらの違いを示しています。

[!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]

> [!IMPORTANT]
> 出力用に指定する反復器は、入力反復器`parallel_transform`と完全に重なり合うか、またはまったくオーバーラップしない必要があります。 入力と出力の反復子が部分的に重なっている場合、このアルゴリズムの動作は指定されません。

### <a name="the-parallel_reduce-algorithm"></a><a name="parallel_reduce"></a>parallel_reduceアルゴリズム

この`parallel_reduce`アルゴリズムは、連想プロパティを満たす一連の操作がある場合に便利です。 (このアルゴリズムでは、可換プロパティは必要ありません)。では、`parallel_reduce`次の操作を実行できます。

- 行列のシーケンスを乗算して行列を生成します。

- ベクトルに行列のシーケンスを掛け合わせて、ベクトルを生成します。

- 文字列のシーケンスの長さを計算します。

- 文字列などの要素のリストを 1 つの要素に結合します。

次の基本的な例は、アルゴリズムを`parallel_reduce`使用して文字列のシーケンスを 1 つの文字列に結合する方法を示しています。 `parallel_transform`の例と同様に、この基本的な例ではパフォーマンスの向上は期待できません。

[!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]

多くの場合、アルゴリズムを`parallel_reduce`[同時実行::combinable](../../parallel/concrt/reference/combinable-class.md)クラスと共`parallel_for_each`に使用するための短縮形と考えることができます。

### <a name="example-performing-map-and-reduce-in-parallel"></a><a name="map_reduce_example"></a>例: マップの実行と並列の削減

*マップ*操作では、シーケンス内の各値に関数が適用されます。 *reduce*操作は、シーケンスの要素を 1 つの値に結合します。 C++ 標準ライブラリ[std::transform](../../standard-library/algorithm-functions.md#transform)および[std::累積](../../standard-library/numeric-functions.md#accumulate)関数を使用して、マップを実行し、操作を削減できます。 ただし、多くの問題に対しては、`parallel_transform`このアルゴリズムを使用してマップ操作を並列に`parallel_reduce`実行し、アルゴリズムは並列で削減操作を実行できます。

次の例では、素数の合計を逐次的および並列に計算するのにかかる時間を比較します。 マップフェーズでは、非素数値が 0 に変換され、減相が値を合計します。

[!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]

マップを実行し、操作を並列で削減する別の例については、「[方法: マップを実行して操作を並列に縮小する](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)」を参照してください。

[[トップ](#top)]

## <a name="partitioning-work"></a><a name="partitions"></a>パーティション分割作業

データ ソースに対する操作を並列化するには、ソースを複数のスレッドが同時にアクセスできる複数のセクションに*分割*する必要があります。 パーティショナーは、並列アルゴリズムがスレッド間の範囲を分割する方法を指定します。 このドキュメントで前述したように、PPL は初期ワークロードを作成し、ワーク・スチール・アルゴリズムと範囲の盗みアルゴリズムを使用して、ワークロードのバランスが崩れているときにこれらのパーティションのバランスを取るデフォルトのパーティション化メカニズムを使用します。 たとえば、あるループ反復処理が一部の反復処理を完了すると、ランタイムは他のスレッドからそのスレッドに作業を再配分します。 ただし、一部のシナリオでは、問題に適した別のパーティション分割メカニズムを指定する必要があります。

、 `parallel_for` `parallel_for_each`、および`parallel_transform`アルゴリズムは、追加のパラメータを受け取る`_Partitioner`オーバーロードされたバージョンを提供します。 このパラメーターは、作業を分割するパーティショナーの種類を定義します。 PPL が定義するパーティショナーの種類を次に示します。

[同時実行::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)<br/>
作業を固定数の範囲 (通常はループで作業できるワーカー スレッドの数) に分割します。 このパーティショナー型は`static_partitioner`に似ていますが、範囲をワーカー スレッドにマップする方法によってキャッシュアフィニティが向上します。 このパーティショナータイプは、ループが同じデータセットで複数回実行され (ループ内のループなど)、データがキャッシュに収まる場合に、パフォーマンスを向上させることができます。 このパーティショナーは、キャンセルに完全には参加しません。 また、協調ブロッキングのセマンティクスを使用しないため、前方依存関係を持つ並列ループでは使用できません。

[同時実行::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)<br/>
範囲の初期数 (通常はループで作業できるワーカー スレッドの数) に作業を分割します。 ランタイムは、パラメーターを受け取るオーバーロードされた並列アルゴリズムを呼び出さない場合に`_Partitioner`、既定でこの型を使用します。 各範囲は、サブ範囲に分割することができ、これにより、ロード・バランシングが行われるようにすることができます。 作業の範囲が完了すると、ランタイムは、他のスレッドからそのスレッドに作業のサブ範囲を再配分します。 ワークロードが他のカテゴリのいずれかに該当しない場合、またはキャンセルまたは協調ブロッキングを完全にサポートする必要がある場合は、このパーティショナーを使用します。

[同時実行::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)<br/>
各範囲が、指定されたチャンク サイズで指定された反復回数以上になるように、処理を範囲に分割します。 このパーティショナータイプはロード バランシングに参加します。ただし、ランタイムは範囲をサブ範囲に分割しません。 各ワーカーについて、ランタイムはキャンセルをチェックし、反復完了後`_Chunk_size`にロード バランシングを実行します。

[同時実行::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)<br/>
作業を固定数の範囲 (通常はループで作業できるワーカー スレッドの数) に分割します。 このパーティショナー型は、作業の盗難を使用しないため、オーバーヘッドが少ないため、パフォーマンスを向上させることができます。 並列ループの各反復が固定された均一な作業を実行し、キャンセルまたは前方協調ブロッキングのサポートを必要としない場合は、このパーティショナータイプを使用します。

> [!WARNING]
> および`parallel_for_each``parallel_transform`アルゴリズムは、静的、単純、およびアフィニティー・パーティショナーに対してランダム・アクセス反復子 (std::[vector](../../standard-library/vector-class.md)など) を使用するコンテナーのみをサポートします。 双方向および前方反復子を使用するコンテナーを使用すると、コンパイル エラーが発生します。 既定のパーティショナー`auto_partitioner`は、これらの 3 つの反復子タイプをすべてサポートします。

通常、これらのパーティショナーは、`affinity_partitioner`以外は同じ方法で使用されます。 ほとんどのパーティショナー型は状態を維持せず、ランタイムによって変更されません。 したがって、次の例に示すように、これらのパーティショナー オブジェクトを呼び出しサイトで作成できます。

[!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]

ただし、将来ループを`affinity_partitioner`再利用するために、アルゴリズムが状態`const`を格納できるように、オブジェクトを非、左辺値の参照として渡す必要があります。 次の例は、データ・セットに対して同じ操作を複数回並列に実行する基本アプリケーションを示しています。 を使用`affinity_partitioner`すると、アレイがキャッシュに収まる可能性があるため、パフォーマンスが向上します。

[!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]

> [!CAUTION]
> または を使用`static_partitioner`する協調ブロッキングセマンティクスに依存する既存のコードを変更する`affinity_partitioner`場合は注意が必要です。 これらのパーティショナータイプは、ロード バランシングや範囲の盗用を使用しないため、アプリケーションの動作を変更する可能性があります。

特定のシナリオでパーティショナーを使用するかどうかを判断する最善の方法は、代表的な負荷とコンピュータ構成の下で操作が完了するまでにかかる時間を試して測定することです。 たとえば、静的パーティション分割は、少数のコアしか持たないマルチコア コンピューターでは速度が飛躍的に向上することがありますが、比較的多くのコアを持つコンピューターでは速度が低下することがあります。

[[トップ](#top)]

## <a name="parallel-sorting"></a><a name="parallel_sorting"></a>並列ソート

PPL は、[同時実行性::pアラレル_ソート](reference/concurrency-namespace-functions.md#parallel_sort)、[同時実行::pアラレル_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)、および[同時実行::parallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort)の 3 つの並べ替えアルゴリズムを提供します。 これらのソート・アルゴリズムは、並列にソートされることからメリットを得られるデータ・セットがある場合に役立ちます。 特に、大きなデータセットがある場合や、計算に値を与える比較演算を使用してデータを並べ替える場合は、並列で並べ替えるのが便利です。 これらのアルゴリズムはそれぞれ、要素を所定の位置に並べ替えます。

`parallel_sort`と`parallel_buffered_sort`アルゴリズムは、両方とも比較ベースのアルゴリズムです。 つまり、要素を値で比較します。 この`parallel_sort`アルゴリズムには追加のメモリ要件はなく、汎用的な並べ替えに適しています。 アルゴリズム`parallel_buffered_sort`は`parallel_sort`より優れたパフォーマンスを発揮できますが、O(N) のスペースが必要です。

アルゴリズム`parallel_radixsort`はハッシュベースです。 つまり、整数キーを使用して要素を並べ替えます。 キーを使用すると、このアルゴリズムは比較を使用する代わりに要素の宛先を直接計算できます。 同様`parallel_buffered_sort`に、このアルゴリズムには O(N) スペースが必要です。

次の表は、3 つの並列ソートアルゴリズムの重要なプロパティをまとめたものです。

|アルゴリズム|説明|ソート機構|ソート安定性|メモリの要件|時間の複雑さ|反復器アクセス|
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|
|`parallel_sort`|汎用比較ベースの並べ替え。|比較ベース (昇順)|不安定|なし|O((N/P)ログ(N/P) + 2N((P-1)/P)|ランダム|
|`parallel_buffered_sort`|O(N) 空間を必要とする、より高速な汎用比較ベースの並べ替え。|比較ベース (昇順)|不安定|追加の O(N) スペースが必要|O((N/P)ログ(N))|ランダム|
|`parallel_radixsort`|O(N) 空間を必要とする整数キーベースのソート。|ハッシュベース|Stable|追加の O(N) スペースが必要|O(N/P)|ランダム|

次の図は、3 つの並列ソートアルゴリズムの重要なプロパティをグラフィカルに示しています。

![並べ替えアルゴリズムの比較](../../parallel/concrt/media/concrt_parallel_sorting.png "並べ替えアルゴリズムの比較")

これらの並列ソートアルゴリズムは、キャンセルと例外処理の規則に従います。 同時実行ランタイムでのキャンセルと例外処理の詳細については、「[並列アルゴリズムのキャンセル](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms)と[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)」を参照してください。

> [!TIP]
> これらの並列ソートアルゴリズムは、移動セマンティクスをサポートします。 移動代入演算子を定義して、スワップ操作をより効率的に実行できます。 移動セマンティクスと移動代入演算子の詳細については、「[右辺値参照宣言子: &&](../../cpp/rvalue-reference-declarator-amp-amp.md)」および「[コンストラクターの移動と代入演算子の移動 (C++)」](../../cpp/move-constructors-and-move-assignment-operators-cpp.md)を参照してください。 移動代入演算子またはスワップ関数を指定しない場合、並べ替えアルゴリズムではコピー コンストラクターが使用されます。

次の基本的な例は、値`parallel_sort`の`int`並べ`vector`替えの使用方法を示しています。 デフォルトでは、`parallel_sort`値を比較するために[std::less を](../../standard-library/less-struct.md)使用します。

[!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]

この例では、カスタム比較関数を提供する方法を示します。 [std::complex:real](../../standard-library/complex-class.md#real)メソッドを使用して[、std::complex\<倍精度](../../standard-library/complex-double.md)浮動小数点型>値を昇順に並べ替えます。

[!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]

この例では、アルゴリズムにハッシュ関数を提供する`parallel_radixsort`方法を示します。 次の使用例は、3-D ポイントを並べ替えます。 ポイントは、参照点からの距離に基づいて並べ替えられます。

[!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]

例として、この例では比較的小さいデータ セットを使用しています。 ベクターの初期サイズを大きくすると、より大きなデータ セットよりもパフォーマンスが向上します。

この例では、ハッシュ関数としてラムダ式を使用します。 また、std: :[ハッシュクラス](../../standard-library/hash-class.md)の組み込み実装のいずれかを使用することも、独自の特殊化を定義することもできます。 この例に示すように、カスタムハッシュ関数オブジェクトを使用することもできます。

[!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]

[!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]

ハッシュ関数は整数型を返す必要があります ([std::is_integral::value](../../standard-library/is-integral-class.md)は**true**にする必要があります ) 。 この整数型は、 型`size_t`に変換可能である必要があります。

### <a name="choosing-a-sorting-algorithm"></a><a name="choose_sort"></a>並べ替えアルゴリズムの選択

多くの場合、`parallel_sort`速度とメモリパフォーマンスの最適なバランスを実現します。 ただし、データ セットのサイズを大きくすると、使用可能なプロセッサの数、比較機能の複雑さ、`parallel_buffered_sort`または`parallel_radixsort`パフォーマンスが向上します。 特定のシナリオでどの並べ替えアルゴリズムを使用するかを決定する最善の方法は、代表的なコンピューター構成で一般的なデータを並べ替える時間を試して測定することです。 並べ替え方法を選択する際は、次のガイドラインに留意してください。

- データ セットのサイズ。 このドキュメントでは、*小さい*データセットに含まれる要素数は 1,000 未満、*中程度*のデータセットには 10,000 ~ 100,000 個の要素が含まれ、*大規模な*データセットには 100,000 個を超える要素が含まれています。

- 比較関数またはハッシュ関数が実行する作業の量。

- 使用可能なコンピューティング リソースの量。

- データ・セットの特性。 たとえば、1 つのアルゴリズムは、既にほぼ並べ替えられているデータに対しては適切に機能しますが、完全に並べ替えられていないデータに対しては適していません。

- チャンク サイズ。 オプション`_Chunk_size`の引数は、アルゴリズムが並列からシリアルソートの実装に切り替わるときに、ソート全体を小さな作業単位に分割するタイミングを指定します。 たとえば、512 を提供する場合、作業単位に 512 個以下の要素が含まれる場合、アルゴリズムはシリアル実装に切り替わります。 シリアル実装では、データを並列処理するために必要なオーバーヘッドが解消されるため、全体的なパフォーマンスが向上します。

使用可能なコンピューティング リソースが多数ある場合や、比較関数やハッシュ関数が比較的大量の作業を実行している場合でも、小さなデータセットを並列で並べ替える価値はありません。 [std::sort](../../standard-library/algorithm-functions.md#sort)関数を使用して、小さなデータセットを並べ替えることができます。 (`parallel_sort`および`parallel_buffered_sort`、`sort`データセットよりも大きいチャンク サイズを指定する場合は呼び出`parallel_buffered_sort`しますが、O(N) 領域を割り当てる必要があり、ロックの競合やメモリ割り当てにより時間がかかることがあります。

メモリを節約する必要がある場合や、メモリ アロケーターがロック競合の対象`parallel_sort`となる場合は、中規模のデータセットを並べ替えるために使用します。 `parallel_sort`追加のスペースは必要ありません。他のアルゴリズムには O(N) スペースが必要です。

中`parallel_buffered_sort`規模のデータセットを並べ替え、アプリケーションが追加の O(N) 空間要件を満たす場合に使用します。 `parallel_buffered_sort`コンピューティング リソースが多い場合や、負荷の高い比較関数やハッシュ関数がある場合に特に便利です。

大`parallel_radixsort`きなデータセットを並べ替える場合や、アプリケーションが追加の O(N) 空間要件を満たすときに使用します。 `parallel_radixsort`同等の比較操作が高価な場合や、両方の操作が高価な場合に特に便利です。

> [!CAUTION]
> 適切なハッシュ関数を実装するには、データセットの範囲と、データセット内の各要素が対応する符号なしの値に変換される方法を知っている必要があります。 ハッシュ操作は符号なしの値に対して動作するため、符号なしハッシュ値を生成できない場合は、別のソート方法を検討してください。

、、、`sort``parallel_sort``parallel_buffered_sort`および 、および のパフォーマンスを`parallel_radixsort`、同じ大きなランダム データ セットと比較する例を次に示します。

[!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]

この例では、並べ替え中に O(N) 空間を割り当`parallel_radixsort`てることが許容可能であると仮定し、このコンピューター構成でこのデータセットで最適なパフォーマンスを発揮します。

[[トップ](#top)]

## <a name="related-topics"></a>関連トピック

|Title|説明|
|-----------|-----------------|
|[方法: parallel_for ループを記述する](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|アルゴリズムを使用して行列`parallel_for`乗算を実行する方法を示します。|
|[方法: parallel_for_each ループを記述する](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|`parallel_for_each`アルゴリズムを使用して[std::array](../../standard-library/array-class-stl.md)オブジェクトの素数の数を並列計算する方法を示します。|
|[方法: 並列呼び出しを使用して並列並べ替えルーチンを記述する](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|`parallel_invoke` アルゴリズムを使用して、バイトニック ソート アルゴリズムのパフォーマンスを向上させる方法について説明します。|
|[方法 : parallel_invokeを使用して並列操作を実行する](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|`parallel_invoke` アルゴリズムを使用して、共有データ ソースに対して複数の操作を実行するプログラムのパフォーマンスを向上させる方法について説明します。|
|[方法: マップ操作と縮小操作を並列実行する](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|`parallel_transform`および`parallel_reduce`アルゴリズムを使用してマップを実行し、ファイル内のワードの出現回数をカウントする操作を減らす方法を示します。|
|[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|同時実行アプリケーションの開発においてスケーラビリティと使いやすさを促進する必須プログラミング モデルを提供する PPL について説明します。|
|[PPL における取り消し処理](cancellation-in-the-ppl.md)|PPL での取り消しの役割、並列処理を取り消す方法、およびタスク グループが取り消されるタイミングを判断する方法について説明します。|
|[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|同時実行ランタイムにおける例外処理の役割について説明します。|

## <a name="reference"></a>リファレンス

[parallel_for 関数](reference/concurrency-namespace-functions.md#parallel_for)

[parallel_for_each 関数](reference/concurrency-namespace-functions.md#parallel_for_each)

[parallel_invoke 関数](reference/concurrency-namespace-functions.md#parallel_invoke)

[affinity_partitioner クラス](../../parallel/concrt/reference/affinity-partitioner-class.md)

[auto_partitioner クラス](../../parallel/concrt/reference/auto-partitioner-class.md)

[simple_partitioner クラス](../../parallel/concrt/reference/simple-partitioner-class.md)

[static_partitioner クラス](../../parallel/concrt/reference/static-partitioner-class.md)

[parallel_sort 関数](reference/concurrency-namespace-functions.md#parallel_sort)

[parallel_buffered_sort 関数](reference/concurrency-namespace-functions.md#parallel_buffered_sort)

[parallel_radixsort 関数](reference/concurrency-namespace-functions.md#parallel_radixsort)
