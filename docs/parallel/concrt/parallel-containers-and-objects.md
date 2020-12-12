---
description: '詳細: 並列コンテナーと並列オブジェクト'
title: 並列コンテナーと並列オブジェクト
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: 2d0b6b491fbe41ea74ad0e6c138cb270558f6e73
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172441"
---
# <a name="parallel-containers-and-objects"></a>並列コンテナーと並列オブジェクト

並列パターンライブラリ (PPL) には、要素へのスレッドセーフなアクセスを提供するいくつかのコンテナーとオブジェクトが含まれています。

*同時実行コンテナー* は、最も重要な操作への同時実行セーフアクセスを提供します。 ここでは、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化、または特定のトラバーサルの順序の保証ではありません。 これらのコンテナーの機能は、C++ 標準ライブラリに用意されているものと似ています。 たとえば、 [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) クラスは [std:: vector](../../standard-library/vector-class.md) クラスに似ていますが、 `concurrent_vector` クラスを使用すると、要素を並行して追加することができます。 同時実行コンテナーは、同じコンテナーに対する読み取りと書き込みの両方のアクセスを必要とする並列コードがある場合に使用します。

*同時実行オブジェクト* は、コンポーネント間で同時に共有されます。 同時実行オブジェクトの状態を並行して計算するプロセスでは、同じ状態を直列に計算する別のプロセスと同じ結果が生成されます。 [Concurrency:: 組み合わせ](../../parallel/concrt/reference/combinable-class.md)可能クラスは、同時実行オブジェクト型の一例です。 `combinable`クラスを使用すると、計算を並列に実行し、その計算を最終結果に結合できます。 ミューテックスなどの同期メカニズムを使用して共有変数またはリソースへのアクセスを同期する場合は、同時実行オブジェクトを使用します。

## <a name="sections"></a><a name="top"></a> 各項

このトピックでは、次の並列コンテナーとオブジェクトについて詳しく説明します。

同時実行コンテナー:

- [concurrent_vector クラス](#vector)

  - [Concurrent_vector と vector の違い](#vector-differences)

  - [同時実行セーフな操作](#vector-safety)

  - [例外の安全性](#vector-exceptions)

- [concurrent_queue クラス](#queue)

  - [Concurrent_queue とキューの違い](#queue-differences)

  - [同時実行セーフな操作](#queue-safety)

  - [反復子のサポート](#queue-iterators)

- [concurrent_unordered_map クラス](#unordered_map)

  - [Concurrent_unordered_map と unordered_map の違い](#map-differences)

  - [同時実行セーフな操作](#map-safety)

- [concurrent_unordered_multimap クラス](#unordered_multimap)

- [concurrent_unordered_set クラス](#unordered_set)

- [concurrent_unordered_multiset クラス](#unordered_multiset)

同時実行オブジェクト:

- [組み合わせ可能クラス](#combinable)

  - [メソッドと機能](#combinable-features)

  - [使用例](#combinable-examples)

## <a name="concurrent_vector-class"></a><a name="vector"></a> concurrent_vector クラス

[Concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)クラスは、 [std:: vector](../../standard-library/vector-class.md)クラスと同様に、要素にランダムにアクセスできるようにするシーケンスコンテナークラスです。 クラスは、 `concurrent_vector` 同時実行セーフの追加および要素アクセス操作を可能にします。 追加操作によって、既存のポインターまたは反復子が無効になることはありません。 反復子アクセスおよび走査操作も同時実行セーフです。 ここでは、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化、または特定のトラバーサルの順序の保証ではありません。

### <a name="differences-between-concurrent_vector-and-vector"></a><a name="vector-differences"></a> Concurrent_vector と vector の違い

`concurrent_vector`クラスはクラスによく似て `vector` います。 オブジェクトに対する追加、要素アクセス、反復子アクセス操作の複雑さは、 `concurrent_vector` オブジェクトの場合と同じです `vector` 。 次の点は、と `concurrent_vector` の違いを示してい `vector` ます。

- オブジェクトに対する追加、要素アクセス、反復子アクセス、および反復子の走査操作 `concurrent_vector` は、同時実行セーフです。

- 要素は、オブジェクトの末尾にのみ追加でき `concurrent_vector` ます。 `concurrent_vector`クラスは、メソッドを提供しません `insert` 。

- `concurrent_vector`オブジェクトにを追加するときに、[移動セマンティクス](../../cpp/rvalue-reference-declarator-amp-amp.md)は使用されません。

- `concurrent_vector`クラスに `erase` は、メソッドまたはメソッドが用意されていません `pop_back` 。 と同様に `vector` 、 [clear](reference/concurrent-vector-class.md#clear) メソッドを使用して、オブジェクトからすべての要素を削除 `concurrent_vector` します。

- クラスは、 `concurrent_vector` その要素をメモリ内に連続して格納しません。 そのため、 `concurrent_vector` 配列を使用するすべての方法でクラスを使用することはできません。 たとえば、型のという名前の変数の場合、 `v` `concurrent_vector` 式によって未定義の動作が生成され `&v[0]+2` ます。

- クラスは、 `concurrent_vector` [grow_by](reference/concurrent-vector-class.md#grow_by) および [grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least) メソッドを定義します。 これらのメソッドは、同時実行セーフである点を除いて、 [resize](reference/concurrent-vector-class.md#resize) メソッドに似ています。

- `concurrent_vector`オブジェクトを追加したりサイズを変更したりしても、その要素は再配置されません。 これにより、既存のポインターと反復子を同時操作中に有効なままにすることができます。

- ランタイムは、 `concurrent_vector` 型に対して特殊化されたバージョンを定義していません **`bool`** 。

### <a name="concurrency-safe-operations"></a><a name="vector-safety"></a> Concurrency-Safe の操作

オブジェクトのサイズの増加や拡大、またはオブジェクトの要素へのアクセスを行うすべてのメソッド `concurrent_vector` `concurrent_vector` は、同時実行セーフです。 ここでは、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化、または特定のトラバーサルの順序の保証ではありません。 この規則の例外は `resize` メソッドです。

次の表は、 `concurrent_vector` 同時実行セーフである共通のメソッドと演算子を示しています。

:::row:::
   :::column span="":::
      [`at`](reference/concurrent-vector-class.md#at)\
      [`back`](reference/concurrent-vector-class.md#back)\
      [`begin`](reference/concurrent-vector-class.md#begin)\
      [`capacity`](reference/concurrent-vector-class.md#capacity)
   :::column-end:::
   :::column span="":::
      [`empty`](reference/concurrent-vector-class.md#empty)\
      [`end`](reference/concurrent-vector-class.md#end)\
      [`front`](reference/concurrent-vector-class.md#front)\
      [`grow_by`](reference/concurrent-vector-class.md#grow_by)
   :::column-end:::
   :::column span="":::
      [`grow_to_at_least`](reference/concurrent-vector-class.md#grow_to_at_least)\
      [`max_size`](reference/concurrent-vector-class.md#max_size)\
      [`operator[]`](reference/concurrent-vector-class.md#operator_at)\
      [`push_back`](reference/concurrent-vector-class.md#push_back)
   :::column-end:::
   :::column span="":::
      [`rbegin`](reference/concurrent-vector-class.md#rbegin)\
      [`rend`](reference/concurrent-vector-class.md#rend)\
      [`size`](reference/concurrent-vector-class.md#size)
   :::column-end:::
:::row-end:::

ランタイムが C++ 標準ライブラリとの互換性のために提供する操作 (など) `reserve` は、同時実行セーフではありません。 次の表は、同時実行セーフではない共通のメソッドと演算子を示しています。

:::row:::
   :::column span="":::
      [`assign`](reference/concurrent-vector-class.md#assign)\
      [`clear`](reference/concurrent-vector-class.md#clear)
   :::column-end:::
   :::column span="":::
      [`operator=`](reference/concurrent-vector-class.md#operator_eq)\
      [`reserve`](reference/concurrent-vector-class.md#reserve)
   :::column-end:::
   :::column span="":::
      [`resize`](reference/concurrent-vector-class.md#resize)
   :::column-end:::
   :::column span="":::
      [`shrink_to_fit`](reference/concurrent-vector-class.md#shrink_to_fit)
   :::column-end:::
:::row-end:::

既存の要素の値を変更する操作は、同時実行セーフではありません。 [Reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)オブジェクトなどの同期オブジェクトを使用して、同時実行の読み取り操作と書き込み操作を同じデータ要素に同期します。 同期オブジェクトの詳細については、「 [同期データ構造](../../parallel/concrt/synchronization-data-structures.md)」を参照してください。

でを使用する既存のコードを変換すると `vector` `concurrent_vector` 、同時実行操作によってアプリケーションの動作が変更される可能性があります。 たとえば、オブジェクトに対して2つのタスクを同時に実行する次のようなプログラムを考えてみ `concurrent_vector` ます。 最初のタスクは、オブジェクトに要素を追加し `concurrent_vector` ます。 2番目のタスクは、同じオブジェクト内のすべての要素の合計を計算します。

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

メソッドは `end` 同時実行セーフですが、 [push_back](reference/concurrent-vector-class.md#push_back) メソッドを同時に呼び出すと、によって返される値が変更され `end` ます。 反復子が走査する要素の数は不確定です。 このため、このプログラムを実行するたびに、異なる結果が生成される可能性があります。 要素の型が重要でない場合は、との呼び出しの間に競合状態が存在する可能性があり `push_back` `end` ます。 メソッドは、 `end` 割り当てられているが完全には初期化されていない要素を返す場合があります。

### <a name="exception-safety"></a><a name="vector-exceptions"></a> 例外の安全性

拡張操作または割り当て操作によって例外がスローされた場合、オブジェクトの状態は `concurrent_vector` 無効になります。 `concurrent_vector`無効な状態にあるオブジェクトの動作は、特に明記されていない限り、定義されていません。 ただし、デストラクターは、オブジェクトが無効な状態にある場合でも、オブジェクトが割り当てたメモリを常に解放します。

Vector 要素のデータ型は、 `T` 次の要件を満たしている必要があります。 それ以外の場合、クラスの動作 `concurrent_vector` は定義されていません。

- デストラクターは、をスローすることはできません。

- 既定のコンストラクターまたはコピーコンストラクターがをスローした場合、デストラクターはキーワードを使用して宣言する必要がなく、 **`virtual`** ゼロ初期化されたメモリで正しく動作する必要があります。

[[上](#top)]

## <a name="concurrent_queue-class"></a><a name="queue"></a> concurrent_queue クラス

[Concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)クラスは、 [std:: queue](../../standard-library/queue-class.md)クラスと同様に、front 要素と back 要素にアクセスすることができます。 クラスは、 `concurrent_queue` 同時実行セーフなエンキュー操作とデキュー操作を可能にします。 ここでは、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化、または特定のトラバーサルの順序の保証ではありません。 `concurrent_queue`クラスでは、同時実行セーフではない反復子のサポートも提供されます。

### <a name="differences-between-concurrent_queue-and-queue"></a><a name="queue-differences"></a> Concurrent_queue とキューの違い

`concurrent_queue`クラスはクラスによく似て `queue` います。 次の点は、と `concurrent_queue` の違いを示してい `queue` ます。

- オブジェクトに対するエンキュー操作とデキュー操作 `concurrent_queue` は、同時実行セーフです。

- クラスは、 `concurrent_queue` 同時実行セーフではない反復子のサポートを提供します。

- `concurrent_queue`クラスに `front` は、メソッドまたはメソッドが用意されていません `pop` 。 クラスは、 `concurrent_queue` [try_pop](reference/concurrent-queue-class.md#try_pop) メソッドを定義することで、これらのメソッドを置き換えます。

- `concurrent_queue`クラスは、メソッドを提供しません `back` 。 したがって、キューの末尾を参照することはできません。

- クラスは、 `concurrent_queue` メソッドの代わりに [unsafe_size](reference/concurrent-queue-class.md#unsafe_size) メソッドを提供し `size` ます。 `unsafe_size`メソッドは同時実行セーフではありません。

### <a name="concurrency-safe-operations"></a><a name="queue-safety"></a> Concurrency-Safe の操作

オブジェクトに対してエンキューまたはデキューを行うすべて `concurrent_queue` のメソッドは、同時実行セーフです。 ここでは、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化、または特定のトラバーサルの順序の保証ではありません。

次の表は、 `concurrent_queue` 同時実行セーフである共通のメソッドと演算子を示しています。

:::row:::
   :::column span="":::
      [`empty`](reference/concurrent-queue-class.md#empty)
   :::column-end:::
   :::column span="":::
      [`get_allocator`](reference/concurrent-queue-class.md#get_allocator)
   :::column-end:::
   :::column span="":::
      [`push`](reference/concurrent-queue-class.md#push)
   :::column-end:::
   :::column span="":::
      [`try_pop`](reference/concurrent-queue-class.md#try_pop)
   :::column-end:::
:::row-end:::

メソッドは `empty` 同時実行セーフですが、同時実行操作によって、メソッドが返される前にキューが拡大または縮小される場合があり `empty` ます。

次の表は、同時実行セーフではない共通のメソッドと演算子を示しています。

:::row:::
   :::column span="":::
      [`clear`](reference/concurrent-queue-class.md#clear)
   :::column-end:::
   :::column span="":::
      [`unsafe_begin`](reference/concurrent-queue-class.md#unsafe_begin)
   :::column-end:::
   :::column span="":::
      [`unsafe_end`](reference/concurrent-queue-class.md#unsafe_end)
   :::column-end:::
   :::column span="":::
      [`unsafe_size`](reference/concurrent-queue-class.md#unsafe_size)
   :::column-end:::
:::row-end:::

### <a name="iterator-support"></a><a name="queue-iterators"></a> 反復子のサポート

は、 `concurrent_queue` 同時実行セーフではない反復子を提供します。 これらの反復子は、デバッグのためにのみ使用することをお勧めします。

`concurrent_queue`反復子は、前方方向にのみ要素をトラバースします。 次の表は、各反復子がサポートする演算子を示しています。

|演算子|説明|
|--------------|-----------------|
|`operator++`|キューの次の項目に進みます。 この演算子は、前置インクリメントと後置の両方のセマンティクスを提供するためにオーバーロードされています。|
|`operator*`|現在の項目への参照を取得します。|
|`operator->`|現在の項目へのポインターを取得します。|

\[[Top](#top)]

## <a name="concurrent_unordered_map-class"></a><a name="unordered_map"></a> concurrent_unordered_map クラス

[Concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)クラスは、 [std:: unordered_map](../../standard-library/unordered-map-class.md)クラスと同様に、 [std::p air \<const Key, Ty> ](../../standard-library/pair-structure.md)型の要素の可変長シーケンスを制御する連想コンテナークラスです。 順序なしのマップは、キーと値のペアを追加したり、キーで値を参照したりできるディクショナリと考えることができます。 このクラスは、共有コンテナーに同時にアクセスしたり、それに挿入したり、更新したりする必要がある複数のスレッドまたはタスクがある場合に便利です。

次の例は、を使用するための基本的な構造を示して `concurrent_unordered_map` います。 この例では、[' a ', ' i '] の範囲内に文字キーを挿入します。 操作の順序は不明であるため、各キーの最終的な値も不定になります。 ただし、挿入を並列で実行するのは安全です。

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

を使用して `concurrent_unordered_map` map および reduce 操作を並列で実行する例については、「 [方法: マップ操作と縮小操作を並列実行](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)する」を参照してください。

### <a name="differences-between-concurrent_unordered_map-and-unordered_map"></a><a name="map-differences"></a> Concurrent_unordered_map と unordered_map の違い

`concurrent_unordered_map`クラスはクラスによく似て `unordered_map` います。 次の点は、と `concurrent_unordered_map` の違いを示してい `unordered_map` ます。

- 、 `erase` 、 `bucket` `bucket_count` 、およびの各 `bucket_size` メソッドは、それぞれ、、、およびという名前 `unsafe_erase` `unsafe_bucket` `unsafe_bucket_count` `unsafe_bucket_size` です。 `unsafe_`名前付け規則は、これらのメソッドが同時実行セーフではないことを示します。 同時実行の安全性の詳細については、「 [同時実行セーフの操作](#map-safety)」を参照してください。

- 挿入操作では、既存のポインターまたは反復子を無効にしたり、マップ内に既に存在する項目の順序を変更したりすることはできません。 挿入操作と走査操作は同時に実行できます。

- `concurrent_unordered_map` 前方イテレーションのみをサポートします。

- 挿入は、によって返される反復子を無効にしたり、更新したりすることはありません `equal_range` 。 挿入では、範囲の末尾に不等の項目を追加できます。 Begin 反復子が等しい項目を指しています。

デッドロックを回避するために、 `concurrent_unordered_map` メモリアロケーター、ハッシュ関数、またはその他のユーザー定義コードを呼び出すときにロックを保持する方法はありません。 また、ハッシュ関数が同じ値に対して同じキーを常に評価する必要があります。 最適なハッシュ関数は、ハッシュコード空間全体でキーを均等に分散します。

### <a name="concurrency-safe-operations"></a><a name="map-safety"></a> Concurrency-Safe の操作

クラスは、 `concurrent_unordered_map` 同時実行セーフな挿入および要素アクセス操作を可能にします。 挿入操作では、既存のポインターまたは反復子は無効になりません。 反復子アクセスおよび走査操作も同時実行セーフです。 ここでは、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化、または特定のトラバーサルの順序の保証ではありません。 次の表は、同時実行セーフである一般的に使用さ `concurrent_unordered_map` れるメソッドと演算子を示しています。

:::row:::
   :::column span="":::
      [`at`](reference/concurrent-unordered-map-class.md#at)\
      [`begin`](reference/concurrent-unordered-map-class.md#begin)\
      [`cbegin`](reference/concurrent-unordered-map-class.md#cbegin)\
      [`cend`](reference/concurrent-unordered-map-class.md#cend)
   :::column-end:::
   :::column span="":::
      [`count`](reference/concurrent-unordered-map-class.md#count)\
      [`empty`](reference/concurrent-unordered-map-class.md#empty)\
      [`end`](reference/concurrent-unordered-map-class.md#cend)\
      [`equal_range`](reference/concurrent-unordered-map-class.md#equal_range)
   :::column-end:::
   :::column span="":::
      [`find`](reference/concurrent-unordered-map-class.md#find)\
      [`get_allocator`](reference/concurrent-unordered-map-class.md#get_allocator)\
      [`hash_function`](reference/concurrent-unordered-map-class.md#hash_function)\
      [`insert`](reference/concurrent-unordered-map-class.md#insert)
   :::column-end:::
   :::column span="":::
      [`key_eq`](reference/concurrent-unordered-map-class.md#key_eq)\
      [`max_size`](reference/concurrent-unordered-map-class.md#max_size)\
      [`operator[]`](./reference/concurrent-unordered-map-class.md#operator_at)\
      [`size`](reference/concurrent-unordered-map-class.md#size)
   :::column-end:::
:::row-end:::

メソッドは `count` 同時に実行されるスレッドから安全に呼び出すことができますが、新しい値が同時にコンテナーに挿入されると、異なるスレッドが異なる結果を受け取ることがあります。

次の表は、同時実行セーフではない一般的に使用されるメソッドと演算子を示しています。

:::row:::
   :::column span="":::
      [`clear`](reference/concurrent-unordered-map-class.md#clear)\
      [`load_factor`](reference/concurrent-unordered-map-class.md#load_factor)
   :::column-end:::
   :::column span="":::
      [`max_load_factor`](reference/concurrent-unordered-map-class.md#max_load_factor)
   :::column-end:::
   :::column span="":::
      [`operator=`](reference/concurrent-unordered-map-class.md#operator_eq)
   :::column-end:::
   :::column span="":::
      [`rehash`](reference/concurrent-unordered-map-class.md#rehash)
   :::column-end:::
:::row-end:::

これらのメソッドに加えて、で始まるメソッド `unsafe_` も同時実行セーフではありません。

[[上](#top)]

## <a name="concurrent_unordered_multimap-class"></a><a name="unordered_multimap"></a> concurrent_unordered_multimap クラス

[Concurrency:: concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)クラスは、 `concurrent_unordered_map` 複数の値が同じキーにマップされることを除けば、クラスに似ています。 また `concurrent_unordered_map` 、次の点でも異なります。

- [Concurrent_unordered_multimap:: insert](reference/concurrent-unordered-multimap-class.md#insert)メソッドは、ではなく反復子を返し `std::pair<iterator, bool>` ます。

- クラスは、 `concurrent_unordered_multimap` または `operator[]` メソッドを提供しません `at` 。

次の例は、を使用するための基本的な構造を示して `concurrent_unordered_multimap` います。 この例では、[' a ', ' i '] の範囲内に文字キーを挿入します。 `concurrent_unordered_multimap` キーに複数の値を指定できるようにします。

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[上](#top)]

## <a name="concurrent_unordered_set-class"></a><a name="unordered_set"></a> concurrent_unordered_set クラス

[Concurrency:: concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)クラスはクラスによく似て `concurrent_unordered_map` いますが、キーと値のペアの代わりに値を管理する点が異なります。 クラスは、 `concurrent_unordered_set` または `operator[]` メソッドを提供しません `at` 。

次の例は、を使用するための基本的な構造を示して `concurrent_unordered_set` います。 この例では、[' a ', ' i '] の範囲内に文字値を挿入します。 挿入は並行して実行するのが安全です。

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[上](#top)]

## <a name="concurrent_unordered_multiset-class"></a><a name="unordered_multiset"></a> concurrent_unordered_multiset クラス

[Concurrency:: concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)クラスはクラスによく似て `concurrent_unordered_set` いますが、重複する値が許可されている点が異なります。 また `concurrent_unordered_set` 、次の点でも異なります。

- [Concurrent_unordered_multiset:: insert](reference/concurrent-unordered-multiset-class.md#insert)メソッドは、ではなく反復子を返し `std::pair<iterator, bool>` ます。

- クラスは、 `concurrent_unordered_multiset` または `operator[]` メソッドを提供しません `at` 。

次の例は、を使用するための基本的な構造を示して `concurrent_unordered_multiset` います。 この例では、[' a ', ' i '] の範囲内に文字値を挿入します。 `concurrent_unordered_multiset` 値が複数回出現することを許可します。

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[上](#top)]

## <a name="combinable-class"></a><a name="combinable"></a> 組み合わせ可能クラス

[Concurrency:: 組み合わせ](../../parallel/concrt/reference/combinable-class.md)可能クラスは、再利用可能なスレッドローカルストレージを提供します。これにより、きめ細かな計算を実行し、その計算を最終結果にマージできます。 `combinable` オブジェクトは減少変数と考えることができます。

クラスは、 `combinable` 複数のスレッドまたはタスク間で共有されるリソースがある場合に便利です。 クラスは、ロックを使用 `combinable` しない方法で共有リソースへのアクセスを提供することで、共有状態を排除するのに役立ちます。 したがって、このクラスは、複数のスレッドからの共有データへのアクセスを同期するために、ミューテックスなどの同期機構を使用する代わりに使用できます。

### <a name="methods-and-features"></a><a name="combinable-features"></a> メソッドと機能

クラスの重要なメソッドの一部を次の表に示し `combinable` ます。 すべてのクラスメソッドの詳細については `combinable` 、「 [組み合わせ可能クラス](../../parallel/concrt/reference/combinable-class.md)」を参照してください。

|Method|説明|
|------------|-----------------|
|[地元の](reference/combinable-class.md#local)|現在のスレッドコンテキストに関連付けられているローカル変数への参照を取得します。|
|[オフ](reference/combinable-class.md#clear)|オブジェクトからすべてのスレッドローカル変数を削除 `combinable` します。|
|[結合](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|指定された結合関数を使用して、すべてのスレッドローカル計算のセットから最終的な値を生成します。|

クラスは、 `combinable` 最終的にマージされた結果に対してパラメーター化されるテンプレートクラスです。 既定のコンストラクターを呼び出す場合、 `T` テンプレートパラメーターの型には既定のコンストラクターとコピーコンストラクターが必要です。 `T`テンプレートパラメーターの型に既定のコンストラクターがない場合は、初期化関数をパラメーターとして受け取るコンストラクターのオーバーロードされたバージョンを呼び出します。

`combinable`[結合](reference/combinable-class.md#combine)メソッドまたは[combine_each](reference/combinable-class.md#combine_each)メソッドを呼び出した後、オブジェクトに追加のデータを格納できます。 `combine`メソッドとメソッドを複数回呼び出すこともでき `combine_each` ます。 オブジェクト内のローカル値が `combinable` 変更されない場合、 `combine` メソッドとメソッドは、 `combine_each` 呼び出されるたびに同じ結果を生成します。

### <a name="examples"></a><a name="combinable-examples"></a> 使用例

クラスの使用方法の例については `combinable` 、次のトピックを参照してください。

- [方法: 組み合わせを使用してパフォーマンスを向上させる](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [方法: 組み合わせを使用してセットを結合する](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[上](#top)]

## <a name="related-topics"></a>関連トピック

[方法: 並列コンテナーを使用して効率を向上させる](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
並列コンテナーを使用してデータを並列に効率的に格納およびアクセスする方法を示します。

[方法: 組み合わせを使用してパフォーマンスを向上させる](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
クラスを使用して共有状態を排除し、パフォーマンスを向上させる方法について説明し `combinable` ます。

[方法: 組み合わせを使用してセットを結合する](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
関数を使用して、スレッドローカルデータのセットをマージする方法について説明 `combine` します。

[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
PPL について説明します。これは、同時実行アプリケーションを開発するためのスケーラビリティと使いやすさを促進する命令型プログラミングモデルを提供します。

## <a name="reference"></a>リファレンス

[concurrent_vector クラス](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue クラス](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map クラス](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap クラス](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set クラス](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset クラス](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[組み合わせ可能クラス](../../parallel/concrt/reference/combinable-class.md)
