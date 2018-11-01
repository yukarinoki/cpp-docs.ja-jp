---
title: 並列アルゴリズム
ms.date: 11/04/2016
helpviewer_keywords:
- parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
ms.openlocfilehash: 0ad7f67016dcb7d4638de0f159feb23cd1282b19
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445592"
---
# <a name="parallel-algorithms"></a>並列アルゴリズム

並列パターン ライブラリ (PPL) では、データのコレクションに同時に作業を実行するアルゴリズムを提供します。 これらのアルゴリズムでは、C++ 標準ライブラリで提供されるようになります。

並列アルゴリズムは、同時実行ランタイムで既存の機能から構成されます。 たとえば、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムを使用して、 [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)並列ループの反復処理を実行するオブジェクト。 `parallel_for`アルゴリズムのパーティションが使用可能なコンピューティング リソース数、最適な方法で動作します。

##  <a name="top"></a> セクション

- [Parallel_for アルゴリズム](#parallel_for)

- [Parallel_for_each アルゴリズム](#parallel_for_each)

- [Parallel_invoke アルゴリズム](#parallel_invoke)

- [Parallel_transform と parallel_reduce アルゴリズム](#parallel_transform_reduce)

    - [Parallel_transform アルゴリズム](#parallel_transform)

    - [Parallel_reduce アルゴリズム](#parallel_reduce)

    - [例: のマップし、縮小を並行実行します。](#map_reduce_example)

- [作業をパーティション分割](#partitions)

- [並列並べ替え](#parallel_sorting)

    - [並べ替えアルゴリズムの選択](#choose_sort)

##  <a name="parallel_for"></a> Parallel_for アルゴリズム

[Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムが、同じタスクを並列で繰り返し実行します。 これらの各タスクは、イテレーション値でパラメーター化されます。 このアルゴリズムは、そのループのイテレーション間でリソースを共有しないループの本体がある場合に便利です。

`parallel_for`アルゴリズムの並列実行の最適な方法でタスクをパーティション分割します。 ワーク スティー リング アルゴリズムとワークロードのバランスの取れたがない場合にこれらのパーティションのバランスを取るを盗む範囲を使用します。 1 つのループの反復処理が協調的にブロックされると、ランタイムには、現在のスレッドを他のスレッドまたはプロセッサに割り当てられているイテレーションの範囲が再分配します。 同様に、スレッドには、一連のイテレーションが完了すると、ランタイムはそのスレッドを他のスレッドから作業を再分配します。 `parallel_for`アルゴリズムもサポートしています。*並列処理を入れ子になった*します。 1 つの並列ループにもう 1 つの並列ループが含まれている場合、ランタイムは、並列実行の効率的な方法でループ本体の間での処理リソースを調整します。

`parallel_for`アルゴリズムがいくつかのオーバー ロードされたバージョン。 最初のバージョンでは、開始値と終了値でと処理関数 (ラムダ式、関数オブジェクト、または関数ポインター) をとります。 2 番目のバージョンは開始値、終了値、値を手順、および処理関数に、移動します。 この関数の最初のバージョンでは、ステップ値として 1 を使用します。 残りのバージョンが指定することを可能にするパーティショナー オブジェクトになる方法`parallel_for`スレッド間での範囲を分割する必要があります。 パーティショナーは、セクションで詳しく説明[パーティション分割作業](#partitions)このドキュメントで。

多くを変換できる`for`ループを使用して`parallel_for`します。 ただし、`parallel_for`アルゴリズムとは異なります、`for`ステートメントは、次の方法で。

- `parallel_for`アルゴリズム`parallel_for`を事前に決められた順序では、タスクは実行されません。

- `parallel_for`アルゴリズムは、任意の終了条件をサポートしていません。 `parallel_for`アルゴリズムは、反復変数の現在の値が 1 つが停止します。 より小さい`last`します。

- `_Index_type`型パラメーターは整数型である必要があります。 この整数型の署名または署名されていないことができます。

- ループの反復処理は、転送する必要があります。 `parallel_for`アルゴリズムの種類の例外をスローする[std::invalid_argument](../../standard-library/invalid-argument-class.md)場合、`_Step`パラメーターが 1 未満です。

- 例外処理メカニズム、`parallel_for`のデータ型とは異なるアルゴリズムを`for`ループします。 並列ループの本体で複数の例外が同時に発生した場合、ランタイムを伝達を呼び出したスレッドの例外の 1 つだけ`parallel_for`です。 さらに、1 つのループの反復処理では、例外をスローするときに、ランタイムすぐに停止しません、全体的なループ。 代わりに、ループは取り消し済み状態で配置し、ランタイムがまだ開始されていないすべてのタスクを破棄します。 例外処理と並列アルゴリズムの詳細については、次を参照してください。[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)します。

ただし、`parallel_for`アルゴリズムは、任意の終了条件をサポートしていません、取り消しを使用して、すべてのタスクを停止することができます。 キャンセルの詳細については、次を参照してください。 [PPL における取り消し処理](cancellation-in-the-ppl.md)します。

> [!NOTE]
>  負荷分散と取り消しなどの機能のサポートからの結果がループの本体を並列実行の利点を克服可能性がありますいないスケジュール コスト、特にときに、ループの本体が比較的小さい。 パーティショナーを使用して、並列ループで、このオーバーヘッドを最小限に抑えることができます。 詳細については、次を参照してください。[パーティション分割作業](#partitions)このドキュメントで後述します。

### <a name="example"></a>例

次の例の基本的な構造を示しています、`parallel_for`アルゴリズム。 この例では、並列で [1, 5] の範囲内の各値をコンソールに出力します。

[!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
1 2 4 3 5
```

`parallel_for`アルゴリズムは並列内の各項目に対して、値がコンソールに出力する順序によって異なります。

使用する完全な例については、`parallel_for`アルゴリズムを参照してください[方法: parallel_for ループを記述](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)します。

[[トップ](#top)]

##  <a name="parallel_for_each"></a> Parallel_for_each アルゴリズム

[Concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズムは、タスクを並列での C++ 標準ライブラリで提供されるものなど、反復的なコンテナーを実行します。 このアルゴリズムでは、`parallel_for` アルゴリズムで使用されるのと同じ分割ロジックが使用されます。

`parallel_for_each`アルゴリズムが、C++ 標準ライブラリに似ています[std::for_each](../../standard-library/algorithm-functions.md#for_each)点を除いて、アルゴリズム、`parallel_for_each`アルゴリズムでは、タスクを同時に実行します。 などの他の並列アルゴリズム`parallel_for_each`特定の順序では、タスクは実行されません。

ですが、`parallel_for_each`アルゴリズムは前方反復子とランダム アクセス反復子の両方で動作、ランダム アクセス反復子で優れています。

### <a name="example"></a>例

次の例の基本的な構造を示しています、`parallel_for_each`アルゴリズム。 この例では、各値をコンソールに出力を[std::array](../../standard-library/array-class-stl.md)並列オブジェクト。

[!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
4 5 1 2 3
```

`parallel_for_each`アルゴリズムは並列内の各項目に対して、値がコンソールに出力する順序によって異なります。

使用する完全な例については、`parallel_for_each`アルゴリズムを参照してください[方法: parallel_for_each ループを記述](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)します。

[[トップ](#top)]

##  <a name="parallel_invoke"></a> Parallel_invoke アルゴリズム

[Concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)アルゴリズムを並列に一連のタスクを実行します。 各タスクが完了するまでは返されません。 このアルゴリズムは、同時に実行するいくつかの独立したタスクがある場合に便利です。

`parallel_invoke`アルゴリズムは、パラメーターとして、一連の処理関数 (ラムダ関数、関数オブジェクト、または関数ポインター)。 `parallel_invoke`アルゴリズムは 2 つと 10 個のパラメーターの間をオーバー ロードされます。 すべての関数に渡す`parallel_invoke`0 個のパラメーターを受け取る必要があります。

などの他の並列アルゴリズム`parallel_invoke`特定の順序では、タスクは実行されません。 トピック[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)について説明しますが、どのように`parallel_invoke`アルゴリズムに関連するタスクとタスク グループ。

### <a name="example"></a>例

次の例の基本的な構造を示しています、`parallel_invoke`アルゴリズム。 この例では同時に、 `twice` 3 つのローカル変数に関数をコンソールに結果を出力します。

[!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
108 11.2 HelloHello
```

使用して、完全な例について、`parallel_invoke`アルゴリズムを参照してください[方法: parallel.invoke を使用して並列並べ替えルーチンを記述する](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)と[方法: parallel.invoke to Execute Parallel Operations を使用して](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)します。

[[トップ](#top)]

##  <a name="parallel_transform_reduce"></a> Parallel_transform と parallel_reduce アルゴリズム

[Concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)と[concurrency::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)アルゴリズムは、C++ 標準ライブラリ アルゴリズムの並列バージョン[std::transform](../../standard-library/algorithm-functions.md#transform)と[std::accumulate](../../standard-library/numeric-functions.md#accumulate)、それぞれします。 同時実行ランタイムのバージョンは、並列で実行するため、操作の順序が決定されないことを除いて、C++ 標準ライブラリのバージョンと同様に動作します。 並列に処理されてからのパフォーマンスとスケーラビリティのメリットを活用するのに十分な大きさであるセットを操作する場合は、これらのアルゴリズムを使用します。

> [!IMPORTANT]
>  `parallel_transform`と`parallel_reduce`アルゴリズムは、これらの反復子が安定したメモリ アドレスを生成するためにのみランダム アクセス、双方向、および前方反復子をサポートします。 また、これらの反復子を生成する必要があります以外`const`左辺値です。

###  <a name="parallel_transform"></a> Parallel_transform アルゴリズム

使用することができます、`parallel transform`多くのデータ並列処理操作を実行するアルゴリズム。 たとえば、次のように操作できます。

- 画像の明るさを調整し、その他のイメージ処理操作を実行します。

- 合計または 2 つのベクトルのドット積を実行し、ベクトルに対して他の数値計算を実行します。

- 各イテレーションが 1 つのピクセルをレンダリングする必要がありますには参照の 3-D レイ トレースを実行します。

次の例の呼び出しに使用される基本的な構造を示しています、`parallel_transform`アルゴリズム。 この例は、標準の各要素を否定::[ベクター](../../standard-library/vector-class.md) 2 つの方法でオブジェクト。 最初の方法では、ラムダ式を使用します。 2 番目の方法を使用して[std::negate](../../standard-library/negate-struct.md)から派生した[std::unary_function](../../standard-library/unary-function-struct.md)します。

[!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]

> [!WARNING]
>  この例の基本的な使用`parallel_transform`します。 作業関数が大量の作業を実行しないために、この例ではパフォーマンスが著しく増加が予期されていません。

`parallel_transform`アルゴリズムに 2 つのオーバー ロードがあります。 最初のオーバー ロードは、1 つの入力範囲および単項関数を受け取ります。 単項関数を 1 つの引数、関数オブジェクト、またはから派生した型を受け取るラムダ式を指定できます`unary_function`します。 2 番目のオーバー ロードは、2 つの入力範囲および二項関数を受け取ります。 二項関数を 2 つの引数、関数オブジェクト、またはから派生した型を受け取るラムダ式を指定できます[std::binary_function](../../standard-library/binary-function-struct.md)します。 次の例は、これらの違いを示しています。

[!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]

> [!IMPORTANT]
>  出力に対して指定する反復子`parallel_transform`入力反復子を完全に重複するか、すべての重複しない必要があります。 入力と出力反復子が部分的に重なっている場合、このアルゴリズムの動作は指定されていません。

###  <a name="parallel_reduce"></a> Parallel_reduce アルゴリズム

`parallel_reduce`アルゴリズムは、一連の操作を結合のプロパティを満たす必要がある場合に便利です。 (このアルゴリズムは、交換可能なプロパティを必要はありません)。ここで実行できる操作の一部は`parallel_reduce`:

- シーケンスのマトリックスを生成するために行列を乗算します。

- 一連のベクトルを生成するために行列のベクターを乗算します。

- 文字列のシーケンスの長さを計算します。

- 1 つの要素には、文字列などの要素のリストを結合します。

次の基本的な例を使用する方法を示しています、`parallel_reduce`アルゴリズムを 1 つの文字列に文字列のシーケンスを結合します。 例と同様`parallel_transform`、この基本的な例ではパフォーマンスが向上することはありません。

[!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]

多くの場合、考えることができます`parallel_reduce`使用するための短縮形として、`parallel_for_each`アルゴリズムと共に、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラス。

###  <a name="map_reduce_example"></a> 例: のマップし、縮小を並行実行します。

A*マップ*操作では、シーケンス内の各値に関数を適用します。 A*削減*操作がシーケンスに値を 1 つの要素を結合します。 C++ 標準ライブラリを使用する[std::transform](../../standard-library/algorithm-functions.md#transform)と[std::accumulate](../../standard-library/numeric-functions.md#accumulate)マップを実行し、操作を低減する関数。 ただし、多くの問題では、使用できます、`parallel_transform`マップ操作を並列的に実行するためのアルゴリズムと`parallel_reduce`アルゴリズムは並列に reduce 操作を実行します。

次の例では、逐次的および並列の素数の合計の計算にかかる時間を比較します。 マップのフェーズでは、素数以外の値を 0 および reduce のフェーズの合計値を変換します。

[!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]

マップを実行し、並列操作を減らす別の例では、次を参照してください。[方法: 実行のマップと削減の操作を並列](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)します。

[[トップ](#top)]

##  <a name="partitions"></a> 作業をパーティション分割

必須の手順ではデータ ソースでの操作を並列化する*パーティション*ソースを複数のセクションでは複数のスレッドによって同時にアクセスできます。 パーティショナーは、並列アルゴリズムがスレッド間での範囲を分割する方法を指定します。 このドキュメントで前の説明、PPL は、既定の初期のワークロードを作成し、ワーク スティー リング アルゴリズムとワークロードのバランスの取れたがない場合にこれらのパーティションのバランスを取るを盗む範囲を使用するメカニズムをパーティション分割を使用します。 たとえば、1 つのループの反復処理には、一連のイテレーションが完了すると、ランタイムは作業スレッドを他のスレッドから再分配します。 ただし、一部のシナリオでは、問題に適している別のパーティション分割メカニズムを指定する場合があります。

`parallel_for`、 `parallel_for_each`、および`parallel_transform`アルゴリズムにより、追加のパラメーターを取得するオーバー ロードされたバージョン`_Partitioner`します。 このパラメーターは、作業を分割するパーティショナー型を定義します。 PPL を定義するパーティショナーの種類を次に示します。

[concurrency::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)<br/>
分割は、固定数の範囲 (通常、ループの作業に使用できるワーカー スレッドの数) に機能します。 このパーティショナー型に似ています`static_partitioner`がワーカー スレッドに範囲をマップすることによってキャッシュの類似性が向上します。 このパーティショナー型は、ループが複数回 (など、ループ内のループ)、同じデータ セットに対して実行され、データがキャッシュ内に収まる範囲、パフォーマンスを向上できます。 このパーティショナーは、キャンセルに完全に関与しません。 または協調的ブロッキング セマンティクスを使用しないと、順方向の依存関係がある並列ループを使用することはできません。

[concurrency::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)<br/>
分割は、(通常、ループの作業に使用できるワーカー スレッドの数) の範囲数の初期に動作します。 受け取るオーバー ロードされた並列アルゴリズムを呼び出すことはない場合、ランタイムが既定でこの型を使用する`_Partitioner`パラメーター。 各範囲は、のサブ範囲に分類でき、これにより負荷分散を有効にします。 さまざまな作業が完了すると、ランタイムには、作業スレッドを他のスレッドからのサブ範囲が再分配します。 その他のカテゴリのいずれかで、ワークロードが当たるまたはキャンセルまたは協調ブロッキングを完全にサポートが必要な場合は、このパーティショナーを使用します。

[concurrency::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)<br/>
各範囲は、所定のチャンク サイズで指定されているイテレーションの数がある以上になるよう分割作業範囲。 このパーティショナー型が負荷分散に参加します。ただし、ランタイムはサブ範囲に範囲を分割しません。 各 worker には、ランタイムがキャンセルをチェックし、後の負荷分散を実行`_Chunk_size`イテレーションを完了します。

[concurrency::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)<br/>
分割は、固定数の範囲 (通常、ループの作業に使用できるワーカー スレッドの数) に機能します。 このパーティショナー型は、ワーク スティー リングを使用しませんし、オーバーヘッドが少ないが備わっていますので、パフォーマンスを向上できます。 並列ループの各反復処理が固定かつ一貫性のある作業量を実行し、キャンセルのサポートが必要または協調ブロッキングを転送しない場合は、このパーティショナー型を使用します。

> [!WARNING]
>  `parallel_for_each`と`parallel_transform`アルゴリズムはランダム アクセス反復子を使用して、コンテナーのみをサポート (など、std::[ベクター](../../standard-library/vector-class.md)) 静的な単純なおよびアフィニティ パーティショナーの。 双方向で前方反復子を使用して、コンテナーの使用には、コンパイル時エラーが生成されます。 既定のパーティショナー `auto_partitioner`、これらの反復子型の 3 つすべてをサポートしています。

通常、これらのパーティショナーは、同じ方法で以外に使用`affinity_partitioner`します。 ほとんどの種類のパーティショナーは、状態を保持しないと、ランタイムでは変更されません。 したがって、次の例に示すように、呼び出しサイトでは、これらのパーティショナー オブジェクトを作成できます。

[!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]

ただし、渡す必要があります、`affinity_partitioner`オブジェクト以外として`const`左辺値参照アルゴリズムが再利用する将来のループの状態を格納できるようにします。 次の例では、データ セットで同じ操作を複数回並列で実行する基本的なアプリケーションを示します。 使用`affinity_partitioner`配列はキャッシュに適している可能性があるために、パフォーマンスを向上させることができます。

[!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]

> [!CAUTION]
>  使用する協調ブロッキングのセマンティクスに依存している既存のコードを変更するときに、注意を使用して`static_partitioner`または`affinity_partitioner`します。 これらのパーティショナー型では、負荷分散または範囲の盗難、使用しないと、アプリケーションの動作を変更できます。

パーティショナーを特定のシナリオで使用するかどうかを決定する最善の方法が、実験し、典型的な負荷およびコンピューターの構成を完了する操作にかかる時間を計測します。 たとえば、静的パーティション分割は、少数のコアしか持たないマルチコア コンピューターでは速度が飛躍的に向上することがありますが、比較的多くのコアを持つコンピューターでは速度が低下することがあります。

[[トップ](#top)]

##  <a name="parallel_sorting"></a> 並列並べ替え

PPL では、3 つの並べ替えアルゴリズム: [:parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort)、 [concurrency::parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)、および[concurrency::parallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort)します。 並べ替えアルゴリズムこれらは、並列で並べ替えられる効果が得られるデータ セットがある場合に便利です。 具体的には、並列での並べ替えまたは便利です、大規模なデータセットがある場合、計算コストが高い比較操作を使用してデータを並べ替えます。 これらの各アルゴリズムは、配置内の要素を並べ替えます。

`parallel_sort`と`parallel_buffered_sort`アルゴリズムは、両方の比較に基づくアルゴリズム。 要素値を比較します。 `parallel_sort`アルゴリズムは、追加のメモリ要件がありませんし、汎用的な並べ替えに適しています。 `parallel_buffered_sort`アルゴリズムが実行できるよりも優れています`parallel_sort`、o (n) の領域が必要ですが。

`parallel_radixsort`アルゴリズムは、ハッシュ ベースします。 つまり、整数キーを使用して要素を並べ替えます。 キーを使用すると、このアルゴリズムは比較を行うのではなく、要素のコピー先を直接計算できます。 ような`parallel_buffered_sort`、このアルゴリズムには、o (n) の領域が必要です。

次の表では、次の 3 つの並列並べ替えアルゴリズムの重要なプロパティをまとめたものです。

|アルゴリズム|説明|並べ替えのメカニズム|並べ替えの安定性|メモリの要件|時間の複雑さ|反復子アクセス|
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|
|`parallel_sort`|汎用の比較に基づく並べ替え。|比較に基づく (昇順)|不安定です|なし|O((N/P)log(N/P) + 2N((P-1)/P))|ランダム|
|`parallel_buffered_sort`|高速汎用的な比較に基づく並べ替えを o (n) の領域が必要です。|比較に基づく (昇順)|不安定です|追加の o (n) 領域が必要です。|O((N/P)log(N))|ランダム|
|`parallel_radixsort`|整数キーに基づく並べ替えを o (n) の領域が必要です。|ハッシュ ベース|Stable|追加の o (n) 領域が必要です。|O(N/P)|ランダム|

次の図より多くのグラフィックス、3 つの並列並べ替えアルゴリズムの重要なプロパティを示します。

![並べ替えアルゴリズムの比較](../../parallel/concrt/media/concrt_parallel_sorting.png "concrt_parallel_sorting")

これらのアルゴリズムを並列並べ替え取り消しおよび例外処理の規則に従います。 キャンセルと同時実行ランタイムの例外処理の詳細については、次を参照してください。[並列アルゴリズムの取り消し](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms)と[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)します。

> [!TIP]
>  並列並べ替えアルゴリズムこれらは、移動セマンティクスをサポートします。 スワップ操作をより効率的に実行を有効にする移動代入演算子を定義することができます。 移動セマンティクスと、移動代入演算子の詳細については、次を参照してください。[右辺値参照宣言子: & &](../../cpp/rvalue-reference-declarator-amp-amp.md)、および[移動コンス トラクターと移動代入演算子 (C++)](../../cpp/move-constructors-and-move-assignment-operators-cpp.md)します。 移動代入演算子または swap 関数を指定しない場合、並べ替えのアルゴリズムは、コピー コンス トラクターを使用します。

次の基本的な例は、使用する方法を示します`parallel_sort`を並べ替える、`vector`の`int`値。 既定では、`parallel_sort`使用[std::less](../../standard-library/less-struct.md)値を比較します。

[!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]

この例では、カスタム比較関数を提供する方法を示します。 使用して、 [std::complex::real](../../standard-library/complex-class.md#real)を並べ替える方法[std::string\<double >](../../standard-library/complex-double.md)値で昇順に並べ替えます。

[!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]

この例にハッシュ関数を提供する方法を示しています、`parallel_radixsort`アルゴリズム。 この例では、3-D ポイントを並べ替えます。 ポイントが参照ポイントからの距離に基づいて並べ替えられます。

[!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]

図では、この例は、比較的小さなデータ セットを使用します。 大きなデータ セットのパフォーマンスの向上を実験するベクターの初期サイズを増やすことができます。

この例では、ハッシュ関数としてラムダ式を使用します。 Std の組み込みの実装の 1 つを使用することもできます::[hash クラス](../../standard-library/hash-class.md)か、独自の特殊化を定義します。 この例で示すように、カスタム ハッシュ関数オブジェクトを使用することもできます。

[!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]

[!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]

ハッシュ関数は、整数型を返す必要があります ([std::is_integral::value](../../standard-library/is-integral-class.md)あります**true**)。 この整数の型を型に変換できる必要があります`size_t`します。

###  <a name="choose_sort"></a> 並べ替えアルゴリズムの選択

多くの場合、`parallel_sort`速度とメモリのパフォーマンスの最適なバランスを提供します。 ただし、すると、データ セットに、使用可能なプロセッサ数、または、比較関数の複雑さのサイズを増やす`parallel_buffered_sort`または`parallel_radixsort`パフォーマンスを向上します。 特定のシナリオで使用する並べ替えアルゴリズムを決定する最善の方法が、実験し、代表的なコンピューター構成での一般的なデータの並べ替えにかかる時間を計測します。 並べ替え方法を選択するときに、次のガイドラインに留意してください。

- データ セットのサイズ。 このドキュメントで、*小さな*データセットには、1,000 人未満の要素が含まれています、*中*10,000、100,000 の要素の間でデータセットが含まれていると*大きな*データセットが含まれています100,000 以上の要素。

- ハッシュ関数、比較関数を実行する作業量。

- 使用可能なコンピューティング リソースの量。

- データ セットの特性。 たとえばがほぼ既に並べ替えられているデータに適してがもないデータが完全に並べ替えられた 1 つのアルゴリズムを実行しました。

- チャンク サイズ。 省略可能な`_Chunk_size`引数は、作業の小さな単位に細分化される全体的な並べ替えとしてのシリアル並べ替え実装への並列アルゴリズムがときにスイッチを指定します。 たとえば、512 を指定すると、アルゴリズムに切り替わりますシリアル実装作業単位には、512 個以下の要素が含まれている場合。 シリアル実装は、データを並列処理に必要なオーバーヘッドがなくなるために、全体的なパフォーマンスを向上できます。

使用可能なコンピューティング リソースの数が多い、または、比較関数、またはハッシュ関数は、比較的大量の作業を実行します。 ときにも、並列で小規模なデータセットを並べ替えることにあります。 使用することができます[std::sort](../../standard-library/algorithm-functions.md#sort)小規模なデータセットを並べ替えます。 (`parallel_sort`と`parallel_buffered_sort`呼び出し`sort`をデータセット; を超えるチャンク サイズを指定すると、`parallel_buffered_sort`するロックの競合やメモリの割り当てのための追加の時間がかかる場合があります、o (n) の領域を割り当てる必要があります)。

メモリを節約する必要があります、またはメモリ アロケーターは、ロックの競合によってを使用して、`parallel_sort`規模のデータセットの並べ替えにします。 `parallel_sort` 追加の領域は必要ありません。その他のアルゴリズムには、o (n) の領域が必要です。

使用`parallel_buffered_sort`中小規模のデータセットと、アプリケーションが o (n) の追加の領域要件を満たしている場合の並べ替えにします。 `parallel_buffered_sort` コンピューティング リソースの数が多い、または、高価な compare 関数またはハッシュ関数の場合、特に役に立ちます。

使用`parallel_radixsort`大規模なデータセットと、アプリケーションが o (n) の追加の領域要件を満たしている場合の並べ替えにします。 `parallel_radixsort` 等価比較操作が高価な場合、または両方の操作が高価な場合に特に役に立ちます。

> [!CAUTION]
>  優れたハッシュ関数を実装するには、データセットの範囲と、データセット内の各要素を対応する符号なしの値に変換する方法がわかっている必要があります。 ハッシュ操作は、符号なしの値で機能するため、符号なしのハッシュ値を生成できません。 場合に、さまざまな並べ替え方法を検討します。

次の例のパフォーマンスを比較する`sort`、 `parallel_sort`、 `parallel_buffered_sort`、および`parallel_radixsort`ランダムなデータの場合は、同じ大きなセットに対して。

[!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]

この例では、並べ替え中に o (n) 領域の割り当てを満たすものであることを想定していますで`parallel_radixsort`このコンピューターの構成では、このデータセットで最適なを実行します。

[[トップ](#top)]

## <a name="related-topics"></a>関連トピック

|Title|説明|
|-----------|-----------------|
|[方法: parallel_for ループを記述する](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|使用する方法を示しています、`parallel_for`行列の乗算を実行するアルゴリズム。|
|[方法: parallel_for_each ループを記述する](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|使用する方法を示しています、`parallel_for_each`内の素数の数を計算するアルゴリズム、 [std::array](../../standard-library/array-class-stl.md)並列オブジェクト。|
|[方法: 並列呼び出しを使用して並列並べ替えルーチンを記述する](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|`parallel_invoke` アルゴリズムを使用して、バイトニック ソート アルゴリズムのパフォーマンスを向上させる方法について説明します。|
|[方法: Parallel.Invoke を使用して並列操作を実行する](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|`parallel_invoke` アルゴリズムを使用して、共有データ ソースに対して複数の操作を実行するプログラムのパフォーマンスを向上させる方法について説明します。|
|[方法: マップ操作と縮小操作を並列実行する](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|使用する方法を示しています、`parallel_transform`と`parallel_reduce`マップを実行し、ファイル内の単語の出現回数をカウントする操作を低減するアルゴリズム。|
|[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|スケーラビリティと同時実行アプリケーションを開発するためやすさを促進する命令型プログラミング モデルを提供する PPL について説明します。|
|[PPL における取り消し処理](cancellation-in-the-ppl.md)|PPL、並列処理を取り消す方法、およびタスク グループが取り消された場合を判断する方法での取り消し処理の役割について説明します。|
|[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|同時実行ランタイムでの例外処理の役割について説明します。|

## <a name="reference"></a>参照

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

