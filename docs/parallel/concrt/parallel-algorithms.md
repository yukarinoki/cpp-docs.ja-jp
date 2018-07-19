---
title: 並列アルゴリズム |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel algorithms [Concurrency Runtime]
ms.assetid: 045dca7b-4d73-4558-a44c-383b88a28473
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 365acd15c61b52631fc75018ab4c3a017d3eed8f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694886"
---
# <a name="parallel-algorithms"></a>並列アルゴリズム
並列パターン ライブラリ (PPL) では、データのコレクションに同時に作業を実行するアルゴリズムを提供します。 これらのアルゴリズムでは、C++ 標準ライブラリで提供されるようになります。  
  

 並列アルゴリズムは、同時実行ランタイムの既存の機能から構成されます。 たとえば、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムを使用して、 [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)並列ループの反復処理を実行するオブジェクト。 `parallel_for`アルゴリズム パーティションが使用可能なコンピューティング リソース数、最適な方法で動作します。  

  
##  <a name="top"></a> セクション  
  
- [Parallel_for アルゴリズム](#parallel_for)  
  
- [Parallel_for_each アルゴリズム](#parallel_for_each)  
  
- [Parallel_invoke アルゴリズム](#parallel_invoke)  
  
- [Parallel_transform アルゴリズムと parallel_reduce アルゴリズム](#parallel_transform_reduce)  
  
    - [Parallel_transform アルゴリズム](#parallel_transform)  
  
    - [Parallel_reduce アルゴリズム](#parallel_reduce)  
  
    - [例: を実行するマップし、縮小を並行](#map_reduce_example)  
  
- [パーティション分割作業](#partitions)  
  
- [並列並べ替え](#parallel_sorting)  
  
    - [並べ替えアルゴリズムの選択](#choose_sort)  
  
##  <a name="parallel_for"></a> Parallel_for アルゴリズム  

 [Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムが、同じタスクを並列で繰り返し実行します。 これらの各タスクは、イテレーション値によってパラメーター化されます。 このアルゴリズムは、そのループのイテレーション間でリソースを共有しないループの本体がある場合に便利です。  
  
 `parallel_for`アルゴリズムは並列実行に最適な方法でタスクをパーティション分割します。 ワーク スティー リング アルゴリズムとワークロードが分散ではないときにこれらのパーティションのバランスをとるスティー リング範囲を使用します。 1 つのループの反復処理が協調的にブロックされると、ランタイムには、他のスレッドのプロセッサに現在のスレッドに割り当てられているイテレーションの範囲が再分配します。 同様に、スレッドには、一連のイテレーションが完了すると、ランタイムはそのスレッドに他のスレッドから作業を再分配します。 `parallel_for`アルゴリズムもサポートしています。*並列処理を入れ子になった*です。 1 つの並列ループには、別の並列ループが含まれている、ときに、ランタイムは、並列実行に効率的にループ本体の間での処理リソースを調整します。  
  
 `parallel_for`がいくつかのオーバー ロードされたバージョンのアルゴリズムです。 最初のバージョンでは、開始値、終了値、および作業関数 (ラムダ式、関数オブジェクト、または関数ポインター) を取得します。 2 番目のバージョンは、開始値、終了値、値を手順、および処理関数に、かかります。 この関数の最初のバージョンでは、ステップ値として 1 を使用します。 残りのバージョンが指定を可能にする、パーティショナー オブジェクトを受け取る方法`parallel_for`スレッド間での範囲を分割する必要があります。 パーティショナーは、セクションで詳しく説明[パーティション分割作業](#partitions)このドキュメントでします。  
  
 多くを変換できる`for`にループを使用して`parallel_for`です。 ただし、`parallel_for`アルゴリズムとは異なります、`for`次のようにステートメント。  
  
-   `parallel_for`アルゴリズム`parallel_for`あらかじめ決められた順序でタスクを実行しません。  
  
-   `parallel_for`アルゴリズムが任意の終了条件をサポートしていません。 `parallel_for`アルゴリズムを停止して繰り返し変数の現在の値が 1 のときより小さい`last`です。  
  
-   `_Index_type`型パラメーターは整数型である必要があります。 この整数型の符号付きまたは符号なしことができます。  
  
-   ループの反復処理は、転送する必要があります。 `parallel_for`アルゴリズムの種類の例外をスローする[std::invalid_argument](../../standard-library/invalid-argument-class.md)場合、`_Step`パラメーターが 1 より小さい。  
  
-   例外処理メカニズム、`parallel_for`アルゴリズムとは異なる、`for`ループします。 並列ループの本体に複数の例外が同時に発生した場合、ランタイムを伝達を呼び出したスレッドの例外の 1 つだけ`parallel_for`です。 さらに、1 つのループの反復処理では、例外をスローするときに、ランタイムすぐに停止しません、全体的なループ。 代わりに、ループは、取り消された状態に配置され、ランタイムはまだ開始されていないタスクを破棄します。 例外処理と並列アルゴリズムの詳細については、次を参照してください。[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)です。  
  
 ただし、`parallel_for`アルゴリズムが任意の終了条件をサポートしていません、取り消しを使用して、すべてのタスクを停止することができます。 取り消し処理の詳細については、次を参照してください。 [PPL における取り消し処理](cancellation-in-the-ppl.md)です。  
  
> [!NOTE]
>  負荷分散と取り消しなどの機能のサポートからの結果がループの本体を並行して実行の利点を克服可能性がありますいないスケジュール コスト、特にときループの本体は比較的小さいです。 並列ループでパーティショナーを使用して、このオーバーヘッドを最小限に抑えることができます。 詳細については、次を参照してください。[パーティション分割作業](#partitions)このドキュメントで後述します。  
  
### <a name="example"></a>例  
 次の例の基本的な構造を示しています、`parallel_for`アルゴリズムです。 この例は、並列で範囲 [1, 5] の各値をコンソールに出力します。  
  
 [!code-cpp[concrt-parallel-for-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_1.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
```Output  
1 2 4 3 5  
```  
  
 `parallel_for`アルゴリズムは並列で各項目に対して、値がコンソールに出力する順序が異なります。  
  
 使用する完全な例については、`parallel_for`アルゴリズムを参照してください[する方法: parallel_for ループを記述](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="parallel_for_each"></a> Parallel_for_each アルゴリズム  

 [Concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズムは並列での C++ 標準ライブラリで提供されるものなどの反復的なコンテナーでのタスクを実行します。 このアルゴリズムでは、`parallel_for` アルゴリズムで使用されるのと同じ分割ロジックが使用されます。  
  
 `parallel_for_each`アルゴリズムが、C++ 標準ライブラリに似ています[std::for_each](../../standard-library/algorithm-functions.md#for_each)点を除いて、アルゴリズム、`parallel_for_each`アルゴリズムは、タスクを同時に実行します。 などの他の並列アルゴリズム`parallel_for_each`特定の順序でタスクを実行しません。  
  
 ただし、`parallel_for_each`アルゴリズムは前方反復子とランダム アクセス反復子の両方で、動作、ランダム アクセス反復子とパフォーマンスが向上します。  
  
### <a name="example"></a>例  
 次の例の基本的な構造を示しています、`parallel_for_each`アルゴリズムです。 この例では、内の各値をコンソールに出力する[std::array](../../standard-library/array-class-stl.md)並列内のオブジェクト。  
  
 [!code-cpp[concrt-parallel-for-each-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_2.cpp)]  
  
 この例では、次のサンプル出力が生成されます。  
  
```Output  
4 5 1 2 3  
```  
  
 `parallel_for_each`アルゴリズムは並列で各項目に対して、値がコンソールに出力する順序が異なります。  
  
 使用する完全な例については、`parallel_for_each`アルゴリズムを参照してください[する方法: parallel_for_each ループを記述](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="parallel_invoke"></a> Parallel_invoke アルゴリズム  

 [Concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)アルゴリズムは、一連のタスクを並列で実行します。 各タスクが終了するまでは返しません。 このアルゴリズムは、同時に実行する独立したタスクが複数ある場合に便利です。  
  
 `parallel_invoke`アルゴリズムは、そのパラメーターとして、一連の処理関数 (ラムダ関数、関数オブジェクト、または関数ポインター)。 `parallel_invoke`と 2 つの 10 個のパラメーターの間をアルゴリズムがオーバー ロードします。 すべての関数に渡す`parallel_invoke`0 個のパラメーターを受け取る必要があります。  
  
 などの他の並列アルゴリズム`parallel_invoke`特定の順序でタスクを実行しません。 トピック[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)について説明しますが、どのように`parallel_invoke`タスクとタスク グループに関連するアルゴリズム。  
  
### <a name="example"></a>例  
 次の例の基本的な構造を示しています、`parallel_invoke`アルゴリズムです。 この例では同時に、`twice`関数 3 つのローカル変数に結果をコンソールに出力します。  
  
 [!code-cpp[concrt-parallel-invoke-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_3.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
108 11.2 HelloHello  
```  
  
 使用する完全な例については、`parallel_invoke`アルゴリズムを参照してください[する方法: parallel.invoke を使用して並列並べ替えルーチンを記述する](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)と[する方法: 並列操作を実行する parallel.invoke を使用して](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="parallel_transform_reduce"></a> Parallel_transform アルゴリズムと parallel_reduce アルゴリズム  

 [Concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)と[concurrency::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)アルゴリズムは、C++ 標準ライブラリのアルゴリズムの並列バージョン[std::transform](../../standard-library/algorithm-functions.md#transform)と[std::accumulate](../../standard-library/numeric-functions.md#accumulate)、それぞれします。 同時実行ランタイムのバージョンは、並列で実行することもあるために、操作の順序が決定されないことを除き、C++ 標準ライブラリのバージョンと同様に動作します。 並列に処理されてからのパフォーマンスとスケーラビリティのメリットを活用するのに十分な大きさであるセットを使用する場合は、これらのアルゴリズムを使用します。  
  
> [!IMPORTANT]
>  `parallel_transform`と`parallel_reduce`アルゴリズムは、これらの反復子の安定したメモリ アドレスを生成するためにのみランダム アクセス、双方向、および前方反復子をサポートします。 また、これらの反復子を生成する必要があります以外`const`左辺値です。  
  
###  <a name="parallel_transform"></a> Parallel_transform アルゴリズム  
 使用することができます、`parallel transform`さまざまなデータ並列処理操作を実行するアルゴリズム。 たとえば、次のように操作できます。  
  
-   画像の明るさを調整し、その他のイメージの処理操作を実行します。  
  
-   合計 2 つのベクトルのドット積してベクトルに対して他の数値の計算を実行します。  
  
-   3-D 光線のトレースをレンダリングする必要が 1 つのピクセルを各イテレーションがここでは参照を実行します。  
  
 次の例の呼び出しに使用される基本的な構造を示しています、`parallel_transform`アルゴリズムです。 この例は、標準の各要素を符号反転::[ベクター](../../standard-library/vector-class.md)方法は 2 つのオブジェクト。 最初の方法では、ラムダ式を使用します。 2 番目の方法を使用して[std::negate](../../standard-library/negate-struct.md)から派生した[std::unary_function](../../standard-library/unary-function-struct.md)です。  
  
 [!code-cpp[concrt-basic-parallel-transform#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_4.cpp)]  
  
> [!WARNING]
>  この例の基本的な使用`parallel_transform`です。 処理関数では、大量の作業を実行しないために、この例では、大幅なパフォーマンス向上は必要ありません。  
  
 `parallel_transform`アルゴリズム 2 つのオーバー ロードがあります。 最初のオーバー ロードは、1 つの入力の範囲と単項関数を受け取ります。 単項関数を 1 つの引数、関数オブジェクト、またはその派生型を受け取るラムダ式を指定できます`unary_function`です。 2 番目のオーバー ロードは、2 つの入力範囲および二項関数を受け取ります。 二項関数を 2 つの引数、関数オブジェクト、またはその派生型を受け取るラムダ式を指定できます[std::binary_function](../../standard-library/binary-function-struct.md)です。 次の例は、これらの違いを示しています。  
  
 [!code-cpp[concrt-parallel-transform-vectors#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_5.cpp)]  
  
> [!IMPORTANT]
>  出力に対して指定する反復子`parallel_transform`入力反復子を完全に重なるかまったくと重複しない必要があります。 入力と出力反復子が部分的に重なっている場合、このアルゴリズムの動作は指定されません。  
  
###  <a name="parallel_reduce"></a> Parallel_reduce アルゴリズム  
 `parallel_reduce`アルゴリズムは、結合型のプロパティを満たす操作のシーケンスがある場合に便利です。 (このアルゴリズムは不要可換プロパティです。)ここでは、いくつかの操作を実行できる`parallel_reduce`:  
  
-   マトリックスを生成するマトリックスのシーケンスを乗算します。  
  
-   ベクトルを生成するマトリックスのシーケンスによって、ベクトルを乗算します。  
  
-   文字列のシーケンスの長さを計算します。  
  
-   1 つの要素には、文字列などの要素のリストを結合します。  
  
 次の基本的な例を使用する方法を示しています、`parallel_reduce`シーケンスを 1 つの文字列に文字列を結合するアルゴリズム。 例と同様に`parallel_transform`、この基本的な例ではパフォーマンスが向上することはありません。  
  
 [!code-cpp[concrt-basic-parallel-reduce#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_6.cpp)]  
  
 多くの場合は、考えることができます`parallel_reduce`を使用するための短縮形として、`parallel_for_each`アルゴリズムと共に、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラスです。  
  
###  <a name="map_reduce_example"></a> 例: を実行するマップし、縮小を並行  

 A*マップ*操作は、シーケンス内の各値に関数を適用します。 A*削減*操作が 1 つの値をシーケンスの要素を連結します。 C++ 標準ライブラリを使用する[std::transform](../../standard-library/algorithm-functions.md#transform)と[std::accumulate](../../standard-library/numeric-functions.md#accumulate)マップを実行し、操作を減らすために機能します。 ただし、多くの問題では、使用できます、`parallel_transform`アルゴリズムを並列マップ操作を実行して、`parallel_reduce`アルゴリズムは並列で reduce 操作を実行します。  

  
 次の例では、逐次処理と並列に含まれる素数の合計の計算にかかる時間を比較します。 マップのフェーズでは、素数以外の値を 0 と reduce フェーズ合計値を変換します。  
  
 [!code-cpp[concrt-parallel-map-reduce-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_7.cpp)]  
  
 マップを実行し、並列処理を削減する別の例では、次を参照してください。[する方法: マップの実行と操作を並列に減らす](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="partitions"></a> パーティション分割作業  
 重要な手順では、データ ソースに対して操作を並列化*パーティション*ソースを複数のセクションでは複数のスレッドで同時にアクセスできます。 パーティショナーは、並列アルゴリズムがスレッド間での範囲を分割する方法を指定します。 このドキュメントで先に説明した、PPL は、既定値は最初のワークロードを作成し、ワーク スティー リング アルゴリズムとワークロードが分散ではないときにこれらのパーティションのバランスをとるスティー リング範囲を使用するメカニズムをパーティション分割を使用します。 たとえば、1 つのループの反復処理には、一連のイテレーションが完了すると、ランタイムはそのスレッドに他のスレッドから作業を再分配します。 ただし、一部のシナリオについて、問題に適している別のパーティション分割メカニズムを指定する場合があります。  
  
 `parallel_for`、 `parallel_for_each`、および`parallel_transform`アルゴリズムにより、追加のパラメーターを受け取るオーバー ロードされたバージョン`_Partitioner`します。 このパラメーターは、作業を分割するパーティショナー型を定義します。 PPL を定義するパーティショナーの種類を次に示します。  
  
 [concurrency::affinity_partitioner](../../parallel/concrt/reference/affinity-partitioner-class.md)  
 (通常は、ループで動作する使用可能なワーカー スレッドの数) の範囲数が固定に作業時間で割ります。 このパーティショナー型に似ています`static_partitioner`、ワーカー スレッドに範囲をマップする方法でキャッシュの関係が向上します。 このパーティショナー型は、ループが複数回 (など、ループ内のループ)、同じデータ セットに対して実行され、データがキャッシュ内に収まる範囲とパフォーマンスを向上できます。 このパーティショナーは、キャンセルに完全に関与しません。 または協調的ブロッキング セマンティクスを使用しないと、前方依存関係のある並列ループで使用することはできません。  
  
 [concurrency::auto_partitioner](../../parallel/concrt/reference/auto-partitioner-class.md)  
 除算は作業の範囲 (通常は、ループで動作する使用可能なワーカー スレッドの数) の数の初期値をします。 受け取るオーバー ロードされた並列アルゴリズムを呼び出さないと、ランタイムが既定でこの型を使用する`_Partitioner`パラメーター。 各範囲は、サブ範囲は、分割することができ、それによっての負荷分散有効が発生するします。 さまざまな作業が完了すると、ランタイムには、そのスレッドへの他のスレッドから作業のサブ範囲が再分配します。 その他のカテゴリのいずれかで、ワークロードが当てはまりませんまたはキャンセルまたは協調ブロッキングを完全にサポートが必要な場合は、このパーティショナーを使用します。  
  
 [concurrency::simple_partitioner](../../parallel/concrt/reference/simple-partitioner-class.md)  
 除算の作業を範囲になど個々 の範囲がある指定されたチャンク サイズによって指定されているイテレーションの数では、少なくともいます。 このパーティショナー型が負荷分散に参加します。ただし、ランタイムはサブ範囲内に範囲を分割するはありません。 各ワーカーのランタイムがキャンセルをチェックし、後の負荷分散を実行`_Chunk_size`イテレーションを完了します。  
  
 [concurrency::static_partitioner](../../parallel/concrt/reference/static-partitioner-class.md)  
 (通常は、ループで動作する使用可能なワーカー スレッドの数) の範囲数が固定に作業時間で割ります。 このパーティショナー型は、ワーク スティー リングを使用していないために、オーバーヘッドが少ないために、パフォーマンスを向上できます。 並列ループの各反復処理は、固定し、均一な作業量を実行し、キャンセルのサポートを必要としたり、協調ブロッキングを転送しない場合は、このパーティショナー型を使用します。  
  
> [!WARNING]
>  `parallel_for_each`と`parallel_transform`アルゴリズムは、ランダム アクセス反復子を使用してコンテナーのみをサポート (std など::[ベクター](../../standard-library/vector-class.md)) 静的、シンプル ボリューム、およびアフィニティ パーティショナーをします。 双方向および前方反復子を使用するコンテナーの使用には、コンパイル時エラーが生成されます。 既定パーティショナー `auto_partitioner`、これらの反復子型の 3 つすべてをサポートしています。  
  
 通常これらパーティショナー使用、同じ方法で除く`affinity_partitioner`です。 ほとんどのパーティショナー型では、状態を保持しないと、ランタイムでは変更されません。 したがって、次の例に示すように、呼び出しサイトでこれらのパーティショナー オブジェクトを作成できます。  
  
 [!code-cpp[concrt-static-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_8.cpp)]  
  
 ただし、渡す必要があります、`affinity_partitioner`オブジェクト以外として`const`左辺値参照アルゴリズムが再利用する将来のループの状態を保存するためです。 次の例では、複数回を並列でデータ セットで同じ操作を実行する基本的なアプリケーションを示します。 使用`affinity_partitioner`配列はキャッシュに適している可能性があるために、パフォーマンスを向上させることができます。  
  
 [!code-cpp[concrt-affinity-partitioner#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_9.cpp)]  
  
> [!CAUTION]
>  使用する協調的ブロッキング セマンティクスに依存する既存のコードを変更するときに警告を使用して`static_partitioner`または`affinity_partitioner`です。 これらのパーティショナー型では、負荷分散するか、または範囲スティー リングを使用しないと、アプリケーションの動作を変更できます。  
  
 パーティショナーを特定のシナリオで使用するかどうかを判断する最良の方法では、実験し、代表的な負荷とコンピューターの構成を完了する操作に要する時間を測定します。 たとえば、静的パーティション分割は、少数のコアしか持たないマルチコア コンピューターでは速度が飛躍的に向上することがありますが、比較的多くのコアを持つコンピューターでは速度が低下することがあります。  
  
 [[トップ](#top)]  
  
##  <a name="parallel_sorting"></a> 並列並べ替え  

 PPL には、次の 3 つの並べ替えアルゴリズムが用意されて: [:parallel_sort](reference/concurrency-namespace-functions.md#parallel_sort)、 [concurrency::parallel_buffered_sort](reference/concurrency-namespace-functions.md#parallel_buffered_sort)、および[concurrency::parallel_radixsort](reference/concurrency-namespace-functions.md#parallel_radixsort)です。 並べ替えアルゴリズムこれらは、並列で並べ替えられているから利点を活用できるデータ セットがある場合に便利です。 具体的には、並列並べ替えまたは便利です、大規模なデータセットがある場合、計算コストが高い比較操作を使用してデータを並べ替えます。 これらのアルゴリズムの各は、配置内の要素を並べ替えます。  

  
 `parallel_sort`と`parallel_buffered_sort`アルゴリズムは、比較ベースの両方のアルゴリズムです。 値によって、要素を比較します。 `parallel_sort`アルゴリズムが、追加のメモリ要件がないと、汎用的な並べ替え適しています。 `parallel_buffered_sort`アルゴリズムを実行できるよりも高く`parallel_sort`、o (n) の領域が必要ですが、します。  
  
 `parallel_radixsort`アルゴリズムは、ハッシュをベースです。 つまり、整数キーを使用して要素を並べ替えます。 キーを使用すると、このアルゴリズムは直接比較を使用する代わりに、要素のコピー先を計算できます。 同様に`parallel_buffered_sort`、このアルゴリズムには、o (n) の領域が必要です。  
  
 次の表は、次の 3 つの並列並べ替えアルゴリズムの重要なプロパティをまとめたものです。  
  
|アルゴリズム|説明|並べ替えのメカニズム|並べ替えの安定性|メモリの要件|時間の複雑さ|反復子アクセス|  
|---------------|-----------------|-----------------------|--------------------|-------------------------|---------------------|---------------------|  
|`parallel_sort`|汎用の比較に基づく並べ替え。|比較に基づく (昇順)|不安定です|なし|O((N/P)log(N/P) + 2N((P-1)/P))|ランダム|  
|`parallel_buffered_sort`|高速汎用的な比較に基づく並べ替えを o (n) の領域が必要です。|比較に基づく (昇順)|不安定です|追加の o (n) 領域が必要です。|O((N/P)log(N))|ランダム|  
|`parallel_radixsort`|整数キーに基づく並べ替えを o (n) の領域が必要です。|ハッシュ ベース|Stable|追加の o (n) 領域が必要です。|O(N/P)|ランダム|  
  
 次の図より多くのグラフィックス、3 つの並列並べ替えアルゴリズムの重要なプロパティを示します。  
  
 ![並べ替えアルゴリズムの比較](../../parallel/concrt/media/concrt_parallel_sorting.png "concrt_parallel_sorting")  
  
 これらのアルゴリズムを並列並べ替え取り消しおよび例外処理の規則に従います。 取り消し処理および例外処理、同時実行ランタイムの詳細については、次を参照してください。[並列アルゴリズムの取り消し](../../parallel/concrt/cancellation-in-the-ppl.md#algorithms)と[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)です。  
  
> [!TIP]
>  並列並べ替えアルゴリズムこれらは、移動セマンティクスをサポートします。 スワップ操作をより効率的に実行を有効にする移動代入演算子を定義することができます。 移動セマンティクスと、移動代入演算子の詳細については、次を参照してください。[右辺値参照宣言子: & &](../../cpp/rvalue-reference-declarator-amp-amp.md)、および[移動コンス トラクターと移動代入演算子 (C++)](../../cpp/move-constructors-and-move-assignment-operators-cpp.md)です。 移動代入演算子またはスワップ関数を指定しない場合、並べ替えのアルゴリズムは、コピー コンス トラクターを使用します。  
  
 使用する基本的な例を次に示します`parallel_sort`を並べ替える、`vector`の`int`値。 既定では、`parallel_sort`使用[std::less](../../standard-library/less-struct.md)値を比較します。  
  
 [!code-cpp[concrt-basic-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_10.cpp)]  
  
 この例では、カスタム比較関数を提供する方法を示します。 使用して、 [std::complex::real](../../standard-library/complex-class.md#real)を並べ替える方法[:complex\<二重 >](../../standard-library/complex-double.md)値で昇順にします。  
  
 [!code-cpp[concrt-basic-parallel-sort#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_11.cpp)]  
  
 この例にハッシュ関数を提供する方法を示しています、`parallel_radixsort`アルゴリズムです。 この例では、3-D ポイントを並べ替えます。 ポイントは、参照ポイントからの距離に基づいて並べ替えられます。  
  
 [!code-cpp[concrt-parallel-sort-points#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_12.cpp)]  
  
 図では、この例は、比較的小さなデータ セットを使用します。 パフォーマンスの向上より大きなデータ セットをテストするベクターの初期サイズを増やすことができます。  
  
 この例では、ハッシュ関数としてラムダ式を使用します。 Std の組み込みの実装の 1 つを使用することもできます::[hash クラス](../../standard-library/hash-class.md)か、独自の特殊化を定義します。 この例で示すように、カスタムのハッシュ関数オブジェクトを使用することもできます。  
  
 [!code-cpp[concrt-parallel-sort-points#2](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_13.cpp)]  
  
 [!code-cpp[concrt-parallel-sort-points#3](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_14.cpp)]  
  
 ハッシュ関数は、整数型を返す必要があります ([std::is_integral::value](../../standard-library/is-integral-class.md)する必要があります`true`)。 この整数型を型に変換できる必要があります`size_t`です。  
  
###  <a name="choose_sort"></a> 並べ替えアルゴリズムの選択  
 多くの場合、`parallel_sort`速度とメモリのパフォーマンスの最適なバランスを提供します。 ただし、すると、データ セットやで利用可能なプロセッサの数、比較関数の複雑さのサイズを増やす`parallel_buffered_sort`または`parallel_radixsort`パフォーマンスが向上することができます。 最善の方法を特定のシナリオで使用する並べ替えアルゴリズムを決定するのには実験し、代表的なコンピューター構成での一般的なデータの並べ替えにかかる時間を測定します。 並べ替え方法を選択するときに、次のガイドラインに留意してください。  
  
-   データ セットのサイズ。 このドキュメントで、*小さな*データセットには、数は 1,000 未満の要素が含まれている、*中*10,000 と 100,000 の要素の間でデータセットが含まれていると*大きな*データセットが含まれています100,000 以上の要素です。  
  
-   比較関数またはハッシュ関数を実行する作業の量。  
  
-   使用可能なコンピューティング リソースの量。  
  
-   データ セットの特性。 たとえば、1 つのアルゴリズム可能性があります実行は実行がほぼ既に並べ替えられているデータに対して適切もありませんのないデータを完全に並べ替えられました。  
  
-   チャンクのサイズ。 省略可能な`_Chunk_size`引数は、作業の小さな単位に細分化される全体的な並べ替えに従ってのシリアル並べ替え実装への並列アルゴリズムがときにスイッチを指定します。 たとえば、512 を指定すると、アルゴリズムに切り替わりますシリアル実装作業の単位には、512 個以下の要素が含まれている場合。 シリアル実装は、並列でデータの処理に必要なオーバーヘッドがなくなるために、全体的なパフォーマンスを向上できます。  
  
 使用可能なコンピューティング リソースの数が多いことも、比較関数やハッシュ関数は、比較的大量の作業を実行する際にも並列に小さいデータセットを並べ替えに価値があります。 使用することができます[std::sort](../../standard-library/algorithm-functions.md#sort)小規模なデータセットを並べ替えます。 (`parallel_sort`と`parallel_buffered_sort`呼び出す`sort`データセット; よりも大きいチャンク サイズを指定するときにただし、`parallel_buffered_sort`ロックの競合やメモリの割り当てによりさらに時間がかかる場合があります、o (n) 領域を割り当てる必要があります)。  
  
 メモリを節約する必要があります、またはメモリ アロケーターがロックの競合が対象になりますが、使用`parallel_sort`規模のデータセットの並べ替えにします。 `parallel_sort` 追加の領域は必要ありません。その他のアルゴリズムでは、o (n) の領域が必要です。  
  
 使用して`parallel_buffered_sort`規模のデータセットとアプリケーションが、追加の o (n) 領域の要件を満たしているときの並べ替えにします。 `parallel_buffered_sort` 大量のコンピューティング リソースまたは高価な比較関数またはハッシュ関数がある場合に特に役に立ちます。  
  
 使用して`parallel_radixsort`大規模なデータセットおよびアプリケーションが、追加の o (n) 領域の要件を満たしているときの並べ替えにします。 `parallel_radixsort` 等価の比較操作がより高価な場合や、両方の操作と高価なは、特に役に立ちます。  
  
> [!CAUTION]
>  優れたハッシュ関数を実装するには、データセットの範囲と、データセット内の各要素は対応する符号なしの値に変換される方法がわかっている必要があります。 ハッシュ操作は、符号なしの値で機能するため、符号なしのハッシュ値を生成できません。 場合に、さまざまな並べ替え方法を検討します。  
  
 次の例のパフォーマンスを比較する`sort`、 `parallel_sort`、 `parallel_buffered_sort`、および`parallel_radixsort`ランダムなデータの同じ大きなセットに対してです。  
  
 [!code-cpp[concrt-choosing-parallel-sort#1](../../parallel/concrt/codesnippet/cpp/parallel-algorithms_15.cpp)]  
  
 この例では、o (n) の領域を割り当てて、並べ替え中に許容であることを前提とで`parallel_radixsort`このコンピューターの構成でこのデータセットで最適なを実行します。  
  
 [[トップ](#top)]  
  
## <a name="related-topics"></a>関連トピック  
  
|タイトル|説明|  
|-----------|-----------------|  
|[方法: parallel_for ループを記述する](../../parallel/concrt/how-to-write-a-parallel-for-loop.md)|使用する方法を示します、`parallel_for`行列乗算を実行するアルゴリズム。|  
|[方法: parallel_for_each ループを記述する](../../parallel/concrt/how-to-write-a-parallel-for-each-loop.md)|使用する方法を示します、`parallel_for_each`に含まれる素数の数を計算するアルゴリズム、 [std::array](../../standard-library/array-class-stl.md)並列内のオブジェクト。|  
|[方法: 並列呼び出しを使用して並列並べ替えルーチンを記述する](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)|`parallel_invoke` アルゴリズムを使用して、バイトニック ソート アルゴリズムのパフォーマンスを向上させる方法について説明します。|  
|[方法: Parallel.Invoke を使用して並列操作を実行する](../../parallel/concrt/how-to-use-parallel-invoke-to-execute-parallel-operations.md)|`parallel_invoke` アルゴリズムを使用して、共有データ ソースに対して複数の操作を実行するプログラムのパフォーマンスを向上させる方法について説明します。|  
|[方法: マップ操作と縮小操作を並列実行する](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)|使用する方法を示します、`parallel_transform`と`parallel_reduce`マップを実行し、ファイル内の単語の出現回数をカウントする操作を低減するアルゴリズム。|  
|[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|スケーラビリティと同時実行アプリケーションを開発するためやすさを促進する命令型プログラミング モデルを提供する PPL について説明します。|  
|[PPL における取り消し処理](cancellation-in-the-ppl.md)|PPL、並列処理を取り消す方法、およびタスク グループが取り消されたときを判断する方法でキャンセル処理の役割について説明します。|  
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


