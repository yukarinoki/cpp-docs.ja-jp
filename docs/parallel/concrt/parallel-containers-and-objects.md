---
title: 並列コンテナーとオブジェクト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel objects
- parallel containers
- concurrent containers
ms.assetid: 90ab715c-29cd-48eb-8e76-528619aab466
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cb06cf0c4e3e5868a0dadeefb30c2e75158d4e32
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433387"
---
# <a name="parallel-containers-and-objects"></a>並列コンテナーと並列オブジェクト

並列パターン ライブラリ (PPL) では、いくつかのコンテナーとその要素へのスレッド セーフなアクセスを提供するオブジェクトが含まれています。

A*同時実行コンテナー*最も重要な操作を同時実行セーフなアクセスを提供します。 これらのコンテナーの機能では、C++ 標準ライブラリで提供されるものと似ています。 たとえば、 [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)クラスに似ています、 [std::vector](../../standard-library/vector-class.md)点を除いて、クラス、`concurrent_vector`クラスでは、並列で要素を追加することができます。 読み取りと同じコンテナーへの書き込みアクセスの両方が必要です並列コードがある場合は、同時実行コンテナーを使用します。

A*同時実行オブジェクト*コンポーネント間で同時に共有されます。 並列での同時実行オブジェクトの状態を計算するプロセスには、逐次的に同じ状態を計算する別のプロセスと同じ結果が生成されます。 [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラスは同時実行オブジェクトの型の 1 つの例です。 `combinable`クラスでは、並列で計算を実行して、最終結果には、その計算を結合することができます。 共有変数またはリソースへのアクセスを同期する同期メカニズム、たとえば、ミュー テックスを使用するとそれ以外の場合とは、同時実行オブジェクトを使用します。

##  <a name="top"></a> セクション

このトピックでは、次の並列コンテナーとオブジェクトの詳細について説明します。

同時実行コンテナー:

- [concurrent_vector クラス](#ctor)

   - [Concurrent_vector 間の相違点とベクター](#ctor)

   - [同時実行セーフな操作](#ctor)

   - [例外安全性](#ctor)

- [concurrent_queue クラス](#queue)

   - [Concurrent_queue 違いとキュー](#queue-differences)

   - [同時実行セーフな操作](#queue-safety)

   - [反復子のサポート](#queue-iterators)

- [concurrent_unordered_map クラス](#unordered_map)

   - [Concurrent_unordered_map 違いと unordered_map](#map-differences)

   - [同時実行セーフな操作](#map-safety)

- [concurrent_unordered_multimap クラス](#unordered_multimap)

- [concurrent_unordered_set クラス](#unordered_set)

- [concurrent_unordered_multiset クラス](#unordered_multiset)

同時実行オブジェクト:

- [combinable クラス](#combinable)

   - [メソッドと機能](#combinable-features)

   - [例](#combinable-examples)

##  <a name="vector"></a> concurrent_vector クラス

[Concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)クラスは、シーケンス コンテナー クラスと同じようにする、 [std::vector](../../standard-library/vector-class.md)クラス、その要素にランダムにアクセスすることができます。 `concurrent_vector`クラスを使用する同時実行セーフの追加と要素の操作にアクセスします。 追加操作では、無効の既存のポインターまたは反復子。 反復子のアクセスおよびトラバーサル操作が同時実行セーフもあります。

###  <a name="vector-differences"></a> Concurrent_vector 間の相違点とベクター

`concurrent_vector`クラスによく似ています、`vector`クラス。 追加、要素へのアクセス、および反復子アクセス操作の複雑さを`concurrent_vector`オブジェクトが同じである、`vector`オブジェクト。 次の点は、場所を示しています`concurrent_vector`異なります`vector`:。

- 追加、要素へのアクセス、反復子アクセス、および反復子走査の各操作で、`concurrent_vector`オブジェクトが同時実行セーフです。

- 末尾にのみ要素を追加することができます、`concurrent_vector`オブジェクト。 `concurrent_vector`クラスを提供しません、`insert`メソッド。

- A`concurrent_vector`オブジェクトが使用しない[移動セマンティクス](../../cpp/rvalue-reference-declarator-amp-amp.md)を追加するとします。

- `concurrent_vector`クラスを提供しません、`erase`または`pop_back`メソッド。 同様`vector`を使用して、[オフ](reference/concurrent-vector-class.md#clear)からすべての要素を削除する方法、`concurrent_vector`オブジェクト。

- `concurrent_vector`クラスに保存しません。 その要素連続メモリ。 そのため、使用することはできません、`concurrent_vector`配列を使用できるすべての方法でクラス。 たとえば、という名前の変数`v`型の`concurrent_vector`、式`&v[0]+2`未定義の動作が生成されます。

- `concurrent_vector`クラスを定義、 [grow_by](reference/concurrent-vector-class.md#grow_by)と[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)メソッド。 これらのメソッドのように、[サイズを変更する](reference/concurrent-vector-class.md#resize)メソッドが同時実行セーフです。

- A`concurrent_vector`を追加またはサイズを変更するときに、オブジェクトがその要素を移動できません。 これにより、既存のポインター、反復子の同時操作中に有効なままにします。

- ランタイムに特化したバージョンを定義していない`concurrent_vector`型`bool`します。

###  <a name="vector-safety"></a> 同時実行セーフな操作

すべてのメソッドを追加またはのサイズを大きく、`concurrent_vector`オブジェクト、または内の要素へのアクセス、`concurrent_vector`オブジェクト、同時実行セーフです。 このルールの例外は、`resize`メソッド。

次の表は、一般的な`concurrent_vector`メソッドと同時実行セーフである演算子。

||||
|-|-|-|

|[](reference/concurrent-vector-class.md#at)|[エンド](reference/concurrent-vector-class.md#end)|[演算子&#91;&#93;](reference/concurrent-vector-class.md#operator_at)| |[開始](reference/concurrent-vector-class.md#begin)|[前面](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)| |[戻る](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)| |[容量](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)| |[空](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[サイズ](reference/concurrent-vector-class.md#size)|

たとえば、C++ 標準ライブラリでは、互換性のため、ランタイムを提供する operations `reserve`、同時実行セーフではありません。 次の表は、共通のメソッドと同時実行セーフではない演算子を示します。

|||
|-|-|

|[割り当てる](reference/concurrent-vector-class.md#assign)|[予約](reference/concurrent-vector-class.md#reserve)| |[オフ](reference/concurrent-vector-class.md#clear)|[サイズを変更する](reference/concurrent-vector-class.md#resize)| |[演算子 =](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|

既存の要素の値を変更する操作は、同時実行セーフではありません。 同期オブジェクトを使用して、 [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)同時読み取りを同期操作と書き込みが同じデータ要素を操作するオブジェクト。 同期オブジェクトの詳細については、次を参照してください。[同期データ構造](../../parallel/concrt/synchronization-data-structures.md)します。

使用する既存のコードを変換すると`vector`を使用する`concurrent_vector`、同時実行操作を変更するアプリケーションの動作が発生することができます。 たとえば、次のプログラムを同時に 2 つのタスクを実行する、`concurrent_vector`オブジェクト。 最初のタスクが追加の要素を追加します、`concurrent_vector`オブジェクト。 2 番目のタスクでは、同じオブジェクトのすべての要素の合計を計算します。

[!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]

ただし、`end`メソッドは、同時実行セーフへの同時呼び出し、 [push_back](reference/concurrent-vector-class.md#push_back)メソッドによって返される値は、`end`を変更します。 反復子が走査する要素の数は不確定です。 そのため、このプログラムを生成できます、異なる結果が毎回実行します。

###  <a name="vector-exceptions"></a> 例外安全性

成長または割り当て操作の状態、例外をスロー、`concurrent_vector`オブジェクトは無効になります。 動作を`concurrent_vector`特に明記しない限り、無効な状態になっているオブジェクトが定義されていません。 ただし、デストラクターでは常にオブジェクトによって割り当てられるメモリを解放して、オブジェクトが無効な状態である場合でもです。

ベクターの要素のデータ型`T`、次の要件を満たす必要があります。 それ以外の場合の動作、`concurrent_vector`クラスが定義されていません。

- デストラクターをスローする必要があります。

- 既定値またはコピー コンス トラクターがスローした場合、デストラクター宣言できませんを使用して、`virtual`キーワードおよびその必要があります、ゼロ初期化メモリで正しく機能します。

[[トップ](#top)]

##  <a name="queue"></a> concurrent_queue クラス

[Concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)クラスと同じように、 [std::queue](../../standard-library/queue-class.md)クラス、その前面にアクセスし、要素をバックアップすることができます。 `concurrent_queue`クラスにより同時実行セーフ エンキューとデキュー操作。 `concurrent_queue`クラスでは、同時実行セーフではない反復子のサポートも提供します。

###  <a name="queue-differences"></a> Concurrent_queue 違いとキュー

`concurrent_queue`クラスによく似ています、`queue`クラス。 次の点は、場所を示しています`concurrent_queue`異なります`queue`:。

- エンキューとデキューの操作を`concurrent_queue`オブジェクトが同時実行セーフです。

- `concurrent_queue`クラスは同時実行セーフではない反復子のサポートを提供します。

- `concurrent_queue`クラスを提供しません、`front`または`pop`メソッド。 `concurrent_queue`クラスが定義することでこれらのメソッドを置き換える、 [try_pop](reference/concurrent-queue-class.md#try_pop)メソッド。

- `concurrent_queue`クラスを提供しません、`back`メソッド。 そのため、キューの最後を参照することはできません。

- `concurrent_queue`クラスには、 [unsafe_size](reference/concurrent-queue-class.md#unsafe_size)メソッドの代わりに、`size`メソッド。 `unsafe_size`メソッドは同時実行セーフではありません。

###  <a name="queue-safety"></a> 同時実行セーフな操作

すべてのメソッドにエンキューするまたはからデキューを`concurrent_queue`オブジェクトが同時実行セーフです。

次の表は、一般的な`concurrent_queue`メソッドと同時実行セーフである演算子。

|||
|-|-|
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|

ただし、`empty`メソッドは同時実行セーフ、同時実行操作を拡大または縮小する前にキューが発生する可能性があります、`empty`メソッドを返します。

次の表は、共通のメソッドと同時実行セーフではない演算子を示します。

|||
|-|-|
|[clear](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|

###  <a name="queue-iterators"></a> 反復子のサポート

`concurrent_queue`同時実行セーフではない反復子を提供します。 デバッグの場合のみにこれらの反復子を使用することをお勧めします。

A`concurrent_queue`反復子が順方向のみに要素を走査します。 次の表では、各反復子をサポートする演算子を示します。

|演算子|説明|
|--------------|-----------------|
|`operator++`|キュー内の次の項目に進みます。 この演算子は、前のインクリメントと後置インクリメントの両方のセマンティクスを提供するオーバー ロードします。|
|`operator*`|現在のアイテムへの参照を取得します。|
|`operator->`|現在の項目へのポインターを取得します。|

[[トップ](#top)]

##  <a name="unordered_map"></a> concurrent_unordered_map クラス

[Concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)クラスは、連想コンテナー クラスと同じようにする、 [std::unordered_map](../../standard-library/unordered-map-class.md)クラス、型の要素の可変長シーケンスを制御します。[std::pair\<const Key, Ty >](../../standard-library/pair-structure.md)します。 順序なしのマップにキーと値のペアを追加したり、キーに値を検索しているディクショナリと考えます。 このクラスは、複数のスレッドまたは同時に共有コンテナーへのアクセス、挿入、または更新する必要があるタスクがある場合に便利です。

次の例を使用するための基本的な構造を示しています。`concurrent_unordered_map`します。 この例では、['a'、' i'] の範囲の文字のキーを挿入します。 操作の順序が決定しないため、各キーの最終的な値も不定です。 ただし、並列で、挿入処理を実行しても安全です。

[!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]

使用する例については`concurrent_unordered_map`マップを実行し、並列操作の低減を参照してください。[方法: 実行のマップと削減の操作を並列](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)します。

###  <a name="map-differences"></a> Concurrent_unordered_map 違いと unordered_map

`concurrent_unordered_map`クラスによく似ています、`unordered_map`クラス。 次の点は、場所を示しています`concurrent_unordered_map`異なります`unordered_map`:。

- `erase`、 `bucket`、 `bucket_count`、および`bucket_size`メソッドの名前は`unsafe_erase`、 `unsafe_bucket`、 `unsafe_bucket_count`、および`unsafe_bucket_size`、それぞれします。 `unsafe_`名前付け規則は、これらのメソッドは、同時実行セーフではないことを示します。 同時実行の安全性の詳細については、次を参照してください。[同時実行セーフ操作](#map-safety)します。

- 挿入操作は既存のポインターまたは反復子を無効にも、マップに既に存在する項目の順序を変更しないでください。 挿入し、スキャン操作が同時に発生することができます。

- `concurrent_unordered_map` サポートは、イテレーションのみを転送します。

- カーソルが無効にしたりによって返される反復子を更新していない`equal_range`します。 カーソルは、範囲の末尾に等しくない項目を追加することができます。 Begin 反復子が指す等しい項目。

メソッドを含まない、デッドロックを回避する`concurrent_unordered_map`メモリ アロケーター、ハッシュ関数、またはその他のユーザー定義のコードを呼び出すときにロックを保持します。 また、ハッシュ関数は、同じ値に等しいキーを常に評価を確認する必要があります。 最適なハッシュ関数は、ハッシュ コードの領域間で一様にキーを配布します。

###  <a name="map-safety"></a> 同時実行セーフな操作

`concurrent_unordered_map`クラスは、同時実行セーフ操作が挿入および要素へのアクセスを使用できます。 挿入操作には既存のポインターまたは反復子は無効です。 反復子のアクセスおよびトラバーサル操作が同時実行セーフもあります。 次の表は、一般的に使用される`concurrent_unordered_map`メソッドと同時実行セーフである演算子。

|||||
|-|-|-|-|
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|
|`begin`|`empty`|`get_allocator`|`max_size`|
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|

ただし、`count`からスレッドを同時に実行するメソッドを安全に呼び出すことが、別のスレッドは異なる結果を受信できる場合は、新しい値が、コンテナーに挿入される同時にします。

次の表は、一般的に使用されるメソッドと同時実行セーフではない演算子を示します。

||||
|-|-|-|
|`clear`|`max_load_factor`|`rehash`|
|`load_factor`|[operator=](reference/concurrent-unordered-map-class.md#operator_eq)

これらのメソッドだけでなく任意のメソッドで始まる`unsafe_`もは同時実行セーフにありません。

[[トップ](#top)]

##  <a name="unordered_multimap"></a> concurrent_unordered_multimap クラス

[Concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)クラスによく似ています、`concurrent_unordered_map`クラスが、複数の値を同じキーにマップすることになります。 異なります`concurrent_unordered_map`次のようにします。

- [Concurrent_unordered_multimap::insert](reference/concurrent-unordered-multimap-class.md#insert)メソッドの代わりに、反復子を返します`std::pair<iterator, bool>`します。

- `concurrent_unordered_multimap`クラスを提供しない`operator[]`も`at`メソッド。

次の例を使用するための基本的な構造を示しています。`concurrent_unordered_multimap`します。 この例では、['a'、' i'] の範囲の文字のキーを挿入します。 `concurrent_unordered_multimap` 複数の値を持つキーを使用できます。

[!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]

[[トップ](#top)]

##  <a name="unordered_set"></a> concurrent_unordered_set クラス

[Concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)クラスによく似ています、`concurrent_unordered_map`クラスのキーと値のペアではなく値を管理する点が異なります。 `concurrent_unordered_set`クラスを提供しない`operator[]`も`at`メソッド。

次の例を使用するための基本的な構造を示しています。`concurrent_unordered_set`します。 この例では、['a'、' i'] の範囲の文字の値を挿入します。 並列で、挿入処理を実行しても安全になります。

[!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]

[[トップ](#top)]

##  <a name="unordered_multiset"></a> concurrent_unordered_multiset クラス

[Concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)クラスによく似ています、`concurrent_unordered_set`クラスの重複する値を許可する点が異なります。 異なります`concurrent_unordered_set`次のようにします。

- [Concurrent_unordered_multiset::insert](reference/concurrent-unordered-multiset-class.md#insert)メソッドの代わりに、反復子を返します`std::pair<iterator, bool>`します。

- `concurrent_unordered_multiset`クラスを提供しない`operator[]`も`at`メソッド。

次の例を使用するための基本的な構造を示しています。`concurrent_unordered_multiset`します。 この例では、['a'、' i'] の範囲の文字の値を挿入します。 `concurrent_unordered_multiset` 複数回出現する値を有効にします。

[!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]

[[トップ](#top)]

##  <a name="combinable"></a> combinable クラス

[Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラスを使用する詳細な計算を実行して、その計算を最終結果にマージし、再利用可能なスレッド ローカル ストレージを提供します。 `combinable` オブジェクトは減少変数と考えることができます。

`combinable`クラスは、複数のスレッドまたはタスクの間で共有されるリソースがある場合に便利です。 `combinable`クラスには、ロック制御不要の方法で共有リソースへのアクセスを提供することで、共有状態を回避するのに役立ちます。 そのため、このクラスは、複数のスレッドから共有データへのアクセスを同期する同期メカニズム、たとえば、ミュー テックスを使用する代わりを提供します。

###  <a name="combinable-features"></a> メソッドと機能

次の表にはいくつかの重要なメソッドの`combinable`クラス。 すべての詳細については、`combinable`クラス メソッドを参照してください[combinable クラス](../../parallel/concrt/reference/combinable-class.md)します。

|メソッド|説明|
|------------|-----------------|
|[local](reference/combinable-class.md#local)|現在のスレッド コンテキストに関連付けられているローカル変数への参照を取得します。|
|[clear](reference/combinable-class.md#clear)|すべてのスレッド ローカル変数を削除、`combinable`オブジェクト。|
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|指定された結合関数を使用すると、すべてのスレッド ローカルの計算のセットから最終的な値を生成します。|

`combinable`クラスは、最終的なマージされた結果でパラメーター化されたテンプレート クラスです。 既定のコンス トラクターを呼び出す場合、`T`テンプレート パラメーターの型は、既定のコンス トラクターとコピー コンス トラクターをいる必要があります。 場合、`T`テンプレート パラメーターの型には、既定のコンス トラクターはありません、初期化関数のパラメーターを受け取るコンス トラクターのオーバー ロードされたバージョンを呼び出します。

追加のデータを格納することができます、`combinable`オブジェクトを呼び出した後、[結合](reference/combinable-class.md#combine)または[combine_each](reference/combinable-class.md#combine_each)メソッド。 呼び出すことも、`combine`と`combine_each`メソッドを複数回です。 場合のローカル値はありません、`combinable`オブジェクトの変更を`combine`と`combine_each`メソッドが呼び出されるたびに同じ結果を生成します。

###  <a name="combinable-examples"></a> 例

例を使用する方法については、`combinable`クラスを次のトピックを参照してください。

- [方法: combinable を使用してパフォーマンスを向上させる](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)

- [方法: combinable を使用して集合を結合する](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)

[[トップ](#top)]

## <a name="related-topics"></a>関連トピック

[方法: 並列コンテナーを使用して効率を向上させる](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)<br/>
並列コンテナーを使用して効率的に格納し、並列のデータにアクセスする方法を示します。

[方法: combinable を使用してパフォーマンスを向上させる](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)<br/>
使用する方法を示しています、`combinable`クラスの共有の状態を解消して、パフォーマンスが向上します。

[方法: combinable を使用して集合を結合する](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)<br/>
使用する方法を示しています、`combine`スレッド ローカル データ セットをマージする関数。

[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)<br/>
スケーラビリティと同時実行アプリケーションを開発するためやすさを促進する命令型プログラミング モデルを提供する PPL について説明します。

## <a name="reference"></a>参照

[concurrent_vector クラス](../../parallel/concrt/reference/concurrent-vector-class.md)

[concurrent_queue クラス](../../parallel/concrt/reference/concurrent-queue-class.md)

[concurrent_unordered_map クラス](../../parallel/concrt/reference/concurrent-unordered-map-class.md)

[concurrent_unordered_multimap クラス](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)

[concurrent_unordered_set クラス](../../parallel/concrt/reference/concurrent-unordered-set-class.md)

[concurrent_unordered_multiset クラス](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)

[combinable クラス](../../parallel/concrt/reference/combinable-class.md)
