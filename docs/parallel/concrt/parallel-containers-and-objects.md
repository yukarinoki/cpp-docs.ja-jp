---
title: 並列コンテナーと並列オブジェクト
ms.date: 03/27/2019
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
ms.openlocfilehash: f3fb2bb57c8bcf65de0a7f74f2992050d8257429
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363054"
---
# <a name="parallel-containers-and-objects"></a>並列コンテナーと並列オブジェクト

並列パターン ライブラリ (PPL) には、要素へのスレッド セーフ なアクセスを提供するいくつかのコンテナーとオブジェクトが含まれています。

*同時実行コンテナー*は、最も重要な操作への同時実行セーフ アクセスを提供します。 ここで、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化や特定の走査順序を保証するものではありません。 これらのコンテナーの機能は、C++ 標準ライブラリで提供される機能に似ています。 たとえば、[並行性::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)クラスは[std::vector](../../standard-library/vector-class.md)クラスに似ていますが、`concurrent_vector`クラスでは要素を並列で追加できる点が異なります。 並列コードで、同じコンテナーへの読み取りアクセスと書き込みアクセスの両方を必要とする場合は、同時実行コンテナーを使用します。

*同時実行オブジェクト*は、コンポーネント間で同時に共有されます。 並行オブジェクトの状態を並列計算するプロセスは、同じ状態を逐次計算する別のプロセスと同じ結果を生成します。 [同時実行::combinable](../../parallel/concrt/reference/combinable-class.md)クラスは、同時実行オブジェクト型の一例です。 この`combinable`クラスを使用すると、並列計算を実行し、それらの計算を最終的な結果に結合できます。 同期メカニズム (ミューテックスなど) を使用して共有変数やリソースへのアクセスを同期する場合は、同時実行オブジェクトを使用します。

## <a name="sections"></a><a name="top"></a>セクション

このトピックでは、次の並列コンテナーとオブジェクトについて詳しく説明します。

同時実行コンテナー:

- [concurrent_vectorクラス](#vector)

  - [concurrent_vectorとベクトルの違い](#vector-differences)

  - [同時実行安全操作](#vector-safety)

  - [例外安全性](#vector-exceptions)

- [concurrent_queue クラス](#queue)

  - [concurrent_queueとキューの違い](#queue-differences)

  - [同時実行安全操作](#queue-safety)

  - [反復器のサポート](#queue-iterators)

- [concurrent_unordered_mapクラス](#unordered_map)

  - [concurrent_unordered_mapとunordered_mapの違い](#map-differences)

  - [同時実行安全操作](#map-safety)

- [concurrent_unordered_multimap クラス](#unordered_multimap)

- [concurrent_unordered_set クラス](#unordered_set)

- [concurrent_unordered_multisetクラス](#unordered_multiset)

同時実行オブジェクト:

- [組み合わせ可能なクラス](#combinable)

  - [メソッドと機能](#combinable-features)

  - [例](#combinable-examples)

## <a name="concurrent_vector-class"></a><a name="vector"></a>concurrent_vectorクラス

[同時実行::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)クラスは[、std::vector](../../standard-library/vector-class.md)クラスと同様に、その要素にランダムにアクセスできるシーケンスコンテナクラスです。 この`concurrent_vector`クラスは、同時実行セーフな追加操作と要素アクセス操作を有効にします。 追加操作では、既存のポインターや反復子は無効にされません。 反復子アクセスおよびトラバーサル操作も同時実行セーフです。 ここで、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化や特定の走査順序を保証するものではありません。

### <a name="differences-between-concurrent_vector-and-vector"></a><a name="vector-differences"></a>concurrent_vectorとベクトルの違い

クラス`concurrent_vector`は`vector`クラスによく似ています。 オブジェクトに対する追加、要素アクセス、および反復子アクセス操作の`concurrent_vector`複雑さは、`vector`オブジェクトの場合と同じです。 次の点は、`concurrent_vector`との`vector`違いについて説明しています。

- `concurrent_vector`オブジェクトに対する追加、要素アクセス、反復子アクセス、反復子トラバーサル操作は同時実行セーフです。

- `concurrent_vector`要素は、オブジェクトの末尾にのみ追加できます。 クラス`concurrent_vector`はメソッドを`insert`提供しません。

- オブジェクト`concurrent_vector`に追加するときに、[オブジェクトは移動セマンティクス](../../cpp/rvalue-reference-declarator-amp-amp.md)を使用しません。

- クラス`concurrent_vector`は or`erase``pop_back`メソッドを提供しません。 と同様`vector`に[、clear](reference/concurrent-vector-class.md#clear)メソッドを使用して、オブジェクトから`concurrent_vector`すべての要素を削除します。

- クラス`concurrent_vector`は、その要素をメモリに連続的に格納しません。 したがって、配列を`concurrent_vector`使用できるすべての方法でクラスを使用することはできません。 たとえば、type`v``concurrent_vector`という名前の変数の場合、式`&v[0]+2`は未定義の動作を生成します。

- クラス`concurrent_vector`は[、grow_by](reference/concurrent-vector-class.md#grow_by)と[grow_to_at_leastメソッドを](reference/concurrent-vector-class.md#grow_to_at_least)定義します。 これらのメソッドは、同時実行安全であるという点を除いて[、resize](reference/concurrent-vector-class.md#resize)メソッドに似ています。

- オブジェクト`concurrent_vector`に追加したりサイズを変更したりしても、オブジェクトの要素は再配置されません。 これにより、既存のポインターと反復子は、同時操作中も有効な状態を維持できます。

- ランタイムは 型`concurrent_vector``bool`の特殊なバージョンを定義しません。

### <a name="concurrency-safe-operations"></a><a name="vector-safety"></a>同時実行安全操作

`concurrent_vector`オブジェクトの追加またはサイズの増加、またはオブジェクト内の要素へのアクセスを`concurrent_vector`行うメソッドはすべて、同時実行セーフです。 ここで、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化や特定の走査順序を保証するものではありません。 この規則の例外は`resize`メソッドです。

次の表は、同時`concurrent_vector`実行安全な一般的なメソッドと演算子を示しています。

||||
|-|-|-|
|[で](reference/concurrent-vector-class.md#at)|[end](reference/concurrent-vector-class.md#end)|[operator&#91;&#93;](reference/concurrent-vector-class.md#operator_at)|
|[開始](reference/concurrent-vector-class.md#begin)|[フロント](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|
|[戻る](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|
|[容量](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|
|[empty](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[サイズ](reference/concurrent-vector-class.md#size)|

ランタイムが C++ 標準ライブラリとの互換性を保つために提供する操作`reserve`は、同時実行安全ではありません。 次の表は、同時実行セーフではない一般的なメソッドと演算子を示しています。

|||
|-|-|
|[割り当てる](reference/concurrent-vector-class.md#assign)|[予約](reference/concurrent-vector-class.md#reserve)|
|[クリア](reference/concurrent-vector-class.md#clear)|[resize](reference/concurrent-vector-class.md#resize)|
|[演算子=](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

既存の要素の値を変更する操作は、同時実行セーフではありません。 [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)オブジェクトなどの同期オブジェクトを使用して、同じデータ要素に対する同時読み取りおよび書き込み操作を同期します。 同期オブジェクトの詳細については、「[同期データ構造](../../parallel/concrt/synchronization-data-structures.md)」を参照してください。

を使用`vector``concurrent_vector`して使用する既存のコードを変換すると、同時操作によってアプリケーションの動作が変更される可能性があります。 たとえば、オブジェクトに対して 2 つのタスクを同時に実行`concurrent_vector`する次のプログラムを考えてみます。 最初のタスクでは、オブジェクトに追加の`concurrent_vector`要素を追加します。 2 番目のタスクでは、同じオブジェクト内のすべての要素の合計を計算します。

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

メソッドは同時実行セーフですが[、push_back](reference/concurrent-vector-class.md#push_back)メソッドへの同時呼び出しによって、返`end`される値は変更されます。 `end` 反復子が通過する要素の数は不確定です。 したがって、このプログラムを実行するたびに、異なる結果が生成される可能性があります。 要素型が非自明な場合、呼び出しと呼び出し`push_back``end`の間に競合状態が存在する可能性があります。 この`end`メソッドは、割り当て済みで完全には初期化されていない要素を返す場合があります。

### <a name="exception-safety"></a><a name="vector-exceptions"></a>例外安全性

拡張操作または割り当て操作によって例外がスローされた場合、`concurrent_vector`オブジェクトの状態は無効になります。 無効な状態にある`concurrent_vector`オブジェクトの動作は、特に明記されていない限り、未定義です。 ただし、デストラクターは、オブジェクトが無効な状態であっても、オブジェクトが割り当てるメモリを常に解放します。

ベクター要素のデータ型は、`T`次の要件を満たす必要があります。 それ以外の場合、クラス`concurrent_vector`の動作は未定義です。

- デストラクターはスローできません。

- 既定のコンストラクターまたはコピー コンストラクターがスローする場合、`virtual`デストラクターはキーワードを使用して宣言する必要はありません。

[[トップ](#top)]

## <a name="concurrent_queue-class"></a><a name="queue"></a>concurrent_queueクラス

[std::queue](../../standard-library/queue-class.md)クラスと同じように、[並行性::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)クラスを使用すると、その前面と背面の要素にアクセスできます。 この`concurrent_queue`クラスは、同時実行セーフエンキューおよびデキュー操作を有効にします。 ここで、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化や特定の走査順序を保証するものではありません。 この`concurrent_queue`クラスは、同時実行安全ではない反復機能のサポートも提供します。

### <a name="differences-between-concurrent_queue-and-queue"></a><a name="queue-differences"></a>concurrent_queueとキューの違い

クラス`concurrent_queue`は`queue`クラスによく似ています。 次の点は、`concurrent_queue`との`queue`違いについて説明しています。

- `concurrent_queue`オブジェクトに対するエンキュー操作およびデキュー操作は、同時実行セーフです。

- この`concurrent_queue`クラスは、同時実行安全ではない反復機能のサポートを提供します。

- クラス`concurrent_queue`は or`front``pop`メソッドを提供しません。 クラス`concurrent_queue`は[、try_pop](reference/concurrent-queue-class.md#try_pop)メソッドを定義することによってこれらのメソッドを置き換えます。

- クラス`concurrent_queue`はメソッドを`back`提供しません。 したがって、キューの終わりを参照することはできません。

- クラス`concurrent_queue`は、メソッドではなく[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)メソッドを`size`提供します。 メソッド`unsafe_size`は同時実行セーフではありません。

### <a name="concurrency-safe-operations"></a><a name="queue-safety"></a>同時実行安全操作

オブジェクトへのキューまたはオブジェクトからのキューからのデキューを`concurrent_queue`行うすべてのメソッドは、同時実行セーフです。 ここで、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化や特定の走査順序を保証するものではありません。

次の表は、同時`concurrent_queue`実行安全な一般的なメソッドと演算子を示しています。

|||
|-|-|
|[empty](reference/concurrent-queue-class.md#empty)|[プッシュ](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

`empty`このメソッドは同時実行セーフですが、同時実行操作を実行すると、メソッドが返される前にキュー`empty`が増減する可能性があります。

次の表は、同時実行セーフではない一般的なメソッドと演算子を示しています。

|||
|-|-|
|[クリア](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

### <a name="iterator-support"></a><a name="queue-iterators"></a>反復器のサポート

では`concurrent_queue`、同時実行セーフではない反復子を提供します。 これらの反復子は、デバッグにのみ使用することをお勧めします。

反復`concurrent_queue`子は前方方向にのみ要素を走査します。 各反復器がサポートする演算子を次の表に示します。

|演算子|説明|
|--------------|-----------------|
|`operator++`|キュー内の次の項目に進みます。 この演算子は、プリインクリメントとインクリメント後の両方のセマンティクスを提供するためにオーバーロードされます。|
|`operator*`|現在の項目への参照を取得します。|
|`operator->`|現在の項目へのポインターを取得します。|

[[トップ](#top)]

## <a name="concurrent_unordered_map-class"></a><a name="unordered_map"></a>concurrent_unordered_mapクラス

[同時実行::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)クラスは[、std::unordered_map](../../standard-library/unordered-map-class.md)クラスと同じように[、std::pair\<const Key, Ty>](../../standard-library/pair-structure.md)の要素の可変長シーケンスを制御する連想コンテナー クラスです。 順序なしマップは、キーと値のペアを追加したり、キーで値を検索したりできるディクショナリと考えてください。 このクラスは、共有コンテナーに同時にアクセスする必要がある複数のスレッドまたはタスクがある場合、挿入する、または更新する必要がある場合に便利です。

を使用`concurrent_unordered_map`するための基本的な構造を次の例に示します。 次の使用例は、文字キーを範囲 ['a' ,'i'' に挿入します。 操作の順序が未定であるため、各キーの最終的な値も未定です。 ただし、挿入を並列に実行しても安全です。

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

マップを実行`concurrent_unordered_map`し、操作を並列で削減する例については、「[方法: マップを実行し、操作を並列に縮小する](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)」を参照してください。

### <a name="differences-between-concurrent_unordered_map-and-unordered_map"></a><a name="map-differences"></a>concurrent_unordered_mapとunordered_mapの違い

クラス`concurrent_unordered_map`は`unordered_map`クラスによく似ています。 次の点は、`concurrent_unordered_map`との`unordered_map`違いについて説明しています。

- `erase`、 `bucket`、、`bucket_count`および`bucket_size`メソッドは`unsafe_erase`、 `unsafe_bucket` `unsafe_bucket_count`、 `unsafe_bucket_size`、 、 、 、 、 、 という名前でそれぞれ名前が付けられます。 名前`unsafe_`付け規則は、これらのメソッドが同時実行安全ではないことを示します。 同時実行の安全性の詳細については、「[同時実行安全操作](#map-safety)」を参照してください。

- 挿入操作は、既存のポインターや反復子を無効にしたり、マップに既に存在するアイテムの順序を変更したりしません。 挿入操作とトラバース操作は、同時に実行できます。

- `concurrent_unordered_map`は、順方向反復のみをサポートします。

- 挿入では、 によって`equal_range`返される反復子が無効または更新されることはありません。 挿入では、範囲の末尾に不等項目を追加できます。 開始反復器は等しい項目を指します。

デッドロックを回避するために、メモリ ア`concurrent_unordered_map`ロケーター、ハッシュ関数、またはその他のユーザー定義コードを呼び出すときにロックを保持するメソッドはありません。 また、ハッシュ関数が常に同じ値に等しいキーを評価することを確認する必要があります。 最適なハッシュ関数は、ハッシュ コード空間全体でキーを均等に分散します。

### <a name="concurrency-safe-operations"></a><a name="map-safety"></a>同時実行安全操作

この`concurrent_unordered_map`クラスは、同時実行セーフ挿入および要素アクセス操作を有効にします。 挿入操作では、既存のポインターまたは反復子は無効にされません。 反復子アクセスおよびトラバーサル操作も同時実行セーフです。 ここで、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化や特定の走査順序を保証するものではありません。 次の表は、同時実行`concurrent_unordered_map`安全な一般的に使用されるメソッドと演算子を示しています。

|||||
|-|-|-|-|
|[で](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[挿入](reference/concurrent-unordered-map-class.md#insert)|`size`|

このメソッド`count`は、同時に実行されているスレッドから安全に呼び出すことができますが、新しい値がコンテナーに同時に挿入されると、異なるスレッドが異なる結果を受け取ることができます。

次の表は、同時実行安全でない一般的に使用されるメソッドと演算子を示しています。

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[演算子=](reference/concurrent-unordered-map-class.md#operator_eq)

これらのメソッドに加えて、開始するメソッド`unsafe_`も同時実行セーフではありません。

[[トップ](#top)]

## <a name="concurrent_unordered_multimap-class"></a><a name="unordered_multimap"></a>concurrent_unordered_multimapクラス

[同時実行::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)クラスは、複数の値を`concurrent_unordered_map`同じキーにマップできる点を除いて、クラスによく似ています。 また、次の`concurrent_unordered_map`点とは異なります。

- [concurrent_unordered_multimap::insert](reference/concurrent-unordered-multimap-class.md#insert)メソッドは、 ではなく反復器を返`std::pair<iterator, bool>`します。

- クラス`concurrent_unordered_multimap`は`at`メソッドを提供`operator[]`しません。

を使用`concurrent_unordered_multimap`するための基本的な構造を次の例に示します。 次の使用例は、文字キーを範囲 ['a' ,'i'' に挿入します。 `concurrent_unordered_multimap`キーが複数の値を持つことを可能にします。

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[トップ](#top)]

## <a name="concurrent_unordered_set-class"></a><a name="unordered_set"></a>concurrent_unordered_setクラス

[同時実行::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)クラスは、キーと値`concurrent_unordered_map`のペアではなく値を管理する点を除いて、クラスによく似ています。 クラス`concurrent_unordered_set`は`at`メソッドを提供`operator[]`しません。

を使用`concurrent_unordered_set`するための基本的な構造を次の例に示します。 次の使用例は、文字の値を範囲 ['a' ,'i'' に挿入します。 挿入は並列で行っても安全です。

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[トップ](#top)]

## <a name="concurrent_unordered_multiset-class"></a><a name="unordered_multiset"></a>concurrent_unordered_multisetクラス

[同時実行::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)クラスは、重複する値`concurrent_unordered_set`を許容することを除いて、クラスによく似ています。 また、次の`concurrent_unordered_set`点とは異なります。

- [concurrent_unordered_multiset::insert](reference/concurrent-unordered-multiset-class.md#insert)メソッドは、 の代わりに反復器`std::pair<iterator, bool>`を返します。

- クラス`concurrent_unordered_multiset`は`at`メソッドを提供`operator[]`しません。

を使用`concurrent_unordered_multiset`するための基本的な構造を次の例に示します。 次の使用例は、文字の値を範囲 ['a' ,'i'' に挿入します。 `concurrent_unordered_multiset`を使用すると、値が複数回発生します。

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[トップ](#top)]

## <a name="combinable-class"></a><a name="combinable"></a>組み合わせ可能なクラス

[同時実行::combinable](../../parallel/concrt/reference/combinable-class.md)クラスは、きめ細かい計算を実行し、それらの計算を最終的な結果にマージできる、再利用可能なスレッドローカルストレージを提供します。 `combinable` オブジェクトは減少変数と考えることができます。

この`combinable`クラスは、複数のスレッドまたはタスク間で共有されるリソースがある場合に便利です。 この`combinable`クラスは、ロックフリーで共有リソースにアクセスできるようにすることで、共有状態を排除するのに役立ちます。 したがって、このクラスは、複数のスレッドからの共有データへのアクセスを同期するために、ミューテックスなどの同期メカニズムを使用する代わりに使用できます。

### <a name="methods-and-features"></a><a name="combinable-features"></a>メソッドと機能

次の表に、クラスの重要なメソッドの`combinable`一部を示します。 すべてのクラス メソッドの`combinable`詳細については、「[結合可能なクラス](../../parallel/concrt/reference/combinable-class.md)」を参照してください。

|Method|説明|
|------------|-----------------|
|[local](reference/combinable-class.md#local)|現在のスレッド コンテキストに関連付けられているローカル変数への参照を取得します。|
|[クリア](reference/combinable-class.md#clear)|オブジェクトからすべてのスレッド ローカル変数を`combinable`削除します。|
|[組み合わせる](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|指定された結合関数を使用して、すべてのスレッド ローカル計算のセットから最終的な値を生成します。|

クラス`combinable`は、最終的にマージされた結果にパラメーター化されたテンプレート クラスです。 既定のコンストラクターを呼び出す`T`場合、テンプレート パラメーターの型には、既定のコンストラクターとコピー コンストラクターが必要です。 テンプレート`T`パラメーターの型に既定のコンストラクターがない場合は、初期化関数をパラメーターとして受け取るコンストラクターのオーバーロードされたバージョンを呼び出します。

[結合](reference/combinable-class.md#combine)メソッドまたは[combine_each](reference/combinable-class.md#combine_each)メソッドを呼`combinable`び出した後で、オブジェクトに追加のデータを格納できます。 また、 メソッドと`combine``combine_each`メソッドを複数回呼び出すこともできます。 オブジェクト内のローカル値が`combinable`変更されていない場合、 `combine` `combine_each`メソッドは呼び出されるたびに同じ結果を生成します。

### <a name="examples"></a><a name="combinable-examples"></a>例

`combinable`クラスの使用方法の例については、次のトピックを参照してください。

- [方法: combinable を使用してパフォーマンスを向上させる](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [方法: combinable を使用して集合を結合する](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[トップ](#top)]

## <a name="related-topics"></a>関連トピック

[方法: 並列コンテナーを使用して効率を向上させる](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
並列コンテナーを使用して、データを効率的に格納し、並列にアクセスする方法を示します。

[方法: combinable を使用してパフォーマンスを向上させる](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
クラスを使用して共有`combinable`状態を排除し、パフォーマンスを向上させる方法を示します。

[方法: combinable を使用して集合を結合する](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
関数を`combine`使用してスレッドローカルデータセットをマージする方法を示します。

[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
同時実行アプリケーションの開発においてスケーラビリティと使いやすさを促進する必須プログラミング モデルを提供する PPL について説明します。

## <a name="reference"></a>リファレンス

[concurrent_vectorクラス](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue クラス](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_mapクラス](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap クラス](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set クラス](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multisetクラス](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[組み合わせ可能なクラス](../../parallel/concrt/reference/combinable-class.md)
