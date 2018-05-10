---
title: 並列コンテナーとオブジェクト |Microsoft ドキュメント
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
ms.openlocfilehash: 168705c5d7497a0bcbede505760d49cdb63a3762
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="parallel-containers-and-objects"></a>並列コンテナーと並列オブジェクト
並列パターン ライブラリ (PPL) には、いくつかのコンテナーとその要素にスレッド セーフなアクセスを提供するオブジェクトが含まれています。  
  
 A*同時実行コンテナー*最も重要な操作への同時実行セーフであるアクセスを提供します。 これらのコンテナーの機能では、C++ 標準ライブラリで提供されるようになります。 たとえば、 [::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)クラスに似ています、 [std::vector](../../standard-library/vector-class.md)点を除いて、クラス、`concurrent_vector`クラスでは、並列で要素を追加することができます。 読み取りと同じコンテナーへの書き込みアクセスの両方を必要とする並列コードがある場合は、同時実行コンテナーを使用します。  
  
 A*同時実行オブジェクト*はコンポーネント間で同時に共有します。 並列で同時実行オブジェクトの状態を計算するプロセスは、逐次的に同じ状態を計算する別のプロセスと同じ結果を生成します。 [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラスは、同時実行オブジェクトの種類の一例です。 `combinable`クラスでは、並列で計算を実行して、その計算を最終結果を結合することができます。 共有変数またはリソースへのアクセスを同期するためにミュー テックスなど、同期メカニズムを使用するとそれ以外の場合とは、同時実行オブジェクトを使用します。  
  
##  <a name="top"></a> セクション  
 このトピックでは、次の並列コンテナーとオブジェクトの詳細について説明します。  
  
 同時実行コンテナー:  
  
-   [concurrent_vector クラス](#ctor)  
  
    -   [違い concurrent_vector とベクター](#ctor)  
  
    -   [同時実行セーフな操作](#ctor)  
  
    -   [例外セーフ性](#ctor)  
  
-   [concurrent_queue クラス](#queue)  
  
    -   [Concurrent_queue 違いとキュー](#queue-differences)  
  
    -   [同時実行セーフな操作](#queue-safety)  
  
    -   [反復子のサポート](#queue-iterators)  
  
-   [concurrent_unordered_map クラス](#unordered_map)  
  
    -   [Concurrent_unordered_map 違いと unordered_map](#map-differences)  
  
    -   [同時実行セーフな操作](#map-safety)  
  
-   [concurrent_unordered_multimap クラス](#unordered_multimap)  
  
-   [concurrent_unordered_set クラス](#unordered_set)  
  
-   [concurrent_unordered_multiset クラス](#unordered_multiset)  
  
 同時実行オブジェクト:  
  
-   [combinable クラス](#combinable)  
  
    -   [メソッドと機能](#combinable-features)  
  
    -   [例](#combinable-examples)  
  
##  <a name="vector"></a> concurrent_vector クラス  
 [::Concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)クラスは、シーケンス コンテナー クラスと同じようにする、 [std::vector](../../standard-library/vector-class.md)クラス、その要素にランダムにアクセスすることができます。 `concurrent_vector`と要素のクラスを使用する同時実行セーフな追加の操作にアクセスします。 追加操作では、無効既存のポインターまたは反復子。 反復子アクセス、走査の各操作も同時実行セーフです。  
  
###  <a name="vector-differences"></a> 違い concurrent_vector とベクター  
 `concurrent_vector`クラスとよく似ています、`vector`クラスです。 追加、要素へのアクセス、および反復子アクセス操作の複雑さ、`concurrent_vector`オブジェクトは、同じで、`vector`オブジェクト。 次の点を示します where`concurrent_vector`異なる`vector`:  
  
-   追加、要素へのアクセス、反復子アクセス、反復子走査の各操作で、`concurrent_vector`オブジェクトは、同時実行セーフです。  
  
-   末尾にのみ、要素を追加することができます、`concurrent_vector`オブジェクト。 `concurrent_vector`クラスを提供しない、`insert`メソッドです。  
  
-   A`concurrent_vector`オブジェクトが使用しない[移動セマンティクス](../../cpp/rvalue-reference-declarator-amp-amp.md)に追加するとします。  
  

-   `concurrent_vector`クラスを提供しない、`erase`または`pop_back`メソッドです。 同様に`vector`を使用して、[オフ](reference/concurrent-vector-class.md#clear)からすべての要素を削除する方法、`concurrent_vector`オブジェクト。  
  
-   `concurrent_vector`クラスに保存しません。 その要素連続してメモリです。 したがって、使用することはできません、`concurrent_vector`配列を使用することができます、すべての方法でクラスです。 たとえば、という名前の変数`v`型の`concurrent_vector`、式`&v[0]+2`未定義の動作が生成されます。  
  
-   `concurrent_vector`クラスを定義、 [grow_by](reference/concurrent-vector-class.md#grow_by)と[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)メソッドです。 これらのメソッドのようになります、[サイズを変更する](reference/concurrent-vector-class.md#resize)メソッドが、同時実行セーフです。  
  
-   A`concurrent_vector`を追加またはサイズを変更するときに、オブジェクトがその要素を移動できません。 これにより、既存のポインターとは同時実行操作中に有効なままを指す反復子。  
  
-   ランタイムでの特殊化バージョンが定義されていません`concurrent_vector`型`bool`です。  
  
###  <a name="vector-safety"></a> 同時実行セーフな操作  
 すべてのメソッドを追加するかのサイズを増やして、`concurrent_vector`オブジェクト、または内の要素へのアクセス、`concurrent_vector`オブジェクト、同時実行セーフです。 このルールの例外は、`resize`メソッドです。  
  
 次の表は、一般的な`concurrent_vector`メソッドと同時実行セーフである演算子。  
  
||||  
|-|-|-|  

|[に](reference/concurrent-vector-class.md#at)|[終了](reference/concurrent-vector-class.md#end)|[演算子 & #91、& #93;](reference/concurrent-vector-class.md#operator_at)|  
|[開始](reference/concurrent-vector-class.md#begin)|[前面](reference/concurrent-vector-class.md#front)|[push_back](reference/concurrent-vector-class.md#push_back)|  
|[戻る](reference/concurrent-vector-class.md#back)|[grow_by](reference/concurrent-vector-class.md#grow_by)|[rbegin](reference/concurrent-vector-class.md#rbegin)|  
|[容量](reference/concurrent-vector-class.md#capacity)|[grow_to_at_least](reference/concurrent-vector-class.md#grow_to_at_least)|[rend](reference/concurrent-vector-class.md#rend)|  
|[空](reference/concurrent-vector-class.md#empty)|[max_size](reference/concurrent-vector-class.md#max_size)|[サイズ](reference/concurrent-vector-class.md#size)|  

  
 たとえば、C++ 標準ライブラリでは、互換性のため、ランタイムが提供される操作`reserve`、同時実行セーフではありません。 次の表は、共通のメソッドと同時実行セーフではない演算子を示します。  
  
|||  
|-|-|  

|[割り当てる](reference/concurrent-vector-class.md#assign)|[予約](reference/concurrent-vector-class.md#reserve)|  
|[オフ](reference/concurrent-vector-class.md#clear)|[サイズを変更します。](reference/concurrent-vector-class.md#resize)|  
|[演算子 =](reference/concurrent-vector-class.md#operator_eq)|[shrink_to_fit](reference/concurrent-vector-class.md#shrink_to_fit)|  
  
 既存の要素の値を変更する操作は、同時実行セーフではありません。 など、同期オブジェクトを使用して、 [reader_writer_lock](../../parallel/concrt/reference/reader-writer-lock-class.md)同時読み取りを同期し、同じデータ要素への書き込み操作するオブジェクト。 同期オブジェクトの詳細については、次を参照してください。[同期データ構造](../../parallel/concrt/synchronization-data-structures.md)です。  
  
 使用する既存のコードを変換する際に`vector`を使用する`concurrent_vector`、同時実行操作を変更するアプリケーションの動作が発生することができます。 たとえば、次のプログラムを同時に 2 つのタスクを実行する、`concurrent_vector`オブジェクト。 最初のタスクに追加の要素を追加する、`concurrent_vector`オブジェクト。 2 番目のタスクは、同じオブジェクト内のすべての要素の合計を計算します。  
  
 [!code-cpp[concrt-vector-safety#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_1.cpp)]  
  

 ただし、`end`メソッドは同時実行セーフへの同時呼び出し、 [push_back](reference/concurrent-vector-class.md#push_back)メソッドによって返される値は、`end`を変更します。 反復子を通過する要素の数は予測できません。 そのため、このプログラム結果が生成、異なる実行するたびにします。  
  
###  <a name="vector-exceptions"></a> 例外セーフ性  
 成長または割り当て操作の状態、例外をスロー、`concurrent_vector`オブジェクトは無効になります。 動作、`concurrent_vector`明記しない限り、無効な状態にあるオブジェクトが定義されていません。 ただし、デストラクターでは常にオブジェクトによって割り当てられるメモリを解放して、オブジェクトが無効な状態にある場合。  
  
 ベクトルの要素のデータ型`T`、次の要件を満たす必要があります。 それ以外の場合の動作、`concurrent_vector`クラスが定義されていません。  
  
-   デストラクターがスローする必要があります。  
  
-   既定値またはコピー コンス トラクターをスローする場合、デストラクター宣言できませんを使用して、`virtual`キーワードとその必要があります、メモリがゼロ初期化正しく動作します。  
  
 [[トップ](#top)]  
  
##  <a name="queue"></a> concurrent_queue クラス  
 [Concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)クラスと同じように、 [std::queue](../../standard-library/queue-class.md)クラス、その前にアクセスし、要素をバックアップすることができます。 `concurrent_queue`クラスにより同時実行セーフのエンキューおよびデキューします。 `concurrent_queue`クラスには、同時実行セーフではない反復子のサポートも用意されています。  
  
###  <a name="queue-differences"></a> Concurrent_queue 違いとキュー  
 `concurrent_queue`クラスとよく似ています、`queue`クラスです。 次の点を示します where`concurrent_queue`異なる`queue`:  
  
-   エンキューをデキューし、`concurrent_queue`オブジェクトは、同時実行セーフです。  
  
-   `concurrent_queue`クラスは同時実行セーフではない反復子のサポートを提供します。  
  

-   `concurrent_queue`クラスを提供しない、`front`または`pop`メソッドです。 `concurrent_queue`クラスが定義することによってこれらのメソッドを置き換える、 [try_pop](reference/concurrent-queue-class.md#try_pop)メソッドです。  
  
-   `concurrent_queue`クラスを提供しない、`back`メソッドです。 そのため、キューの最後を参照することはできません。  
  
-   `concurrent_queue`クラスを提供、 [unsafe_size](reference/concurrent-queue-class.md#unsafe_size)メソッドの代わりに、`size`メソッドです。 `unsafe_size`メソッドは同時実行セーフではありません。  

  
###  <a name="queue-safety"></a> 同時実行セーフな操作  
 すべてのメソッドをエンキューするからデキューしたり、`concurrent_queue`オブジェクトは、同時実行セーフです。  
  
 次の表は、一般的な`concurrent_queue`メソッドと同時実行セーフである演算子。  
  
|||  
|-|-|  
|[empty](reference/concurrent-queue-class.md#empty)|[push](reference/concurrent-queue-class.md#push)|  
|[get_allocator](reference/concurrent-queue-class.md#get_allocator)|[try_pop](reference/concurrent-queue-class.md#try_pop)|  


  
 ただし、`empty`メソッドは同時実行セーフでは、同時実行操作を拡大または縮小する前に、キューが発生する可能性があります、`empty`メソッドを返します。  
  
 次の表は、共通のメソッドと同時実行セーフではない演算子を示します。  
  
|||  
|-|-|  
|[clear](reference/concurrent-queue-class.md#clear)|[unsafe_end](reference/concurrent-queue-class.md#unsafe_end)|  
|[unsafe_begin](reference/concurrent-queue-class.md#unsafe_begin)|[unsafe_size](reference/concurrent-queue-class.md#unsafe_size)|  


  
###  <a name="queue-iterators"></a> 反復子のサポート  
 `concurrent_queue`同時実行セーフではない反復子を提供します。 デバッグの場合のみにこれらの反復子を使用することをお勧めします。  
  
 A`concurrent_queue`反復子走査の前方向のみの要素。 次の表は、各反復子をサポートしている演算子を示します。  
  
|演算子|説明|  
|--------------|-----------------|  
|[operator++](http://msdn.microsoft.com/en-us/4cfdd07e-927a-42f8-aaa0-d6881687f413)|キュー内の次の項目に進みます。 この演算子は、前のインクリメントと後置インクリメントの両方のセマンティクスを提供するオーバー ロードします。|  
|[operator*](http://msdn.microsoft.com/en-us/a0e671fc-76e6-4fb4-b95c-ced4dd2b2017)|現在の項目への参照を取得します。|  
|[operator->](http://msdn.microsoft.com/en-us/41fa393d-ae1e-4a38-bb4b-19e8df709ca9)|現在の項目へのポインターを取得します。|  
  
 [[トップ](#top)]  
  
##  <a name="unordered_map"></a> concurrent_unordered_map クラス  
 [ハイパーリンク"file:///C:\\\Users\\\thompet\\\AppData\\\Local\\\Temp\\\DxEditor\\\DduePreview\\\Default\\\798d7037-df37-4310-858b-6f590bbf6ebf\\\HTM\\\html\\\a217b4ac-af2b-4d41-94eb-09a75ee28622"concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)クラスは、連想コンテナーのクラスと同じように、 [std::unordered_map](../../standard-library/unordered-map-class.md)クラス、型の要素の可変長シーケンスを制御[std::pair\<const Key, Ty >](../../standard-library/pair-structure.md)です。 考える順序なしのマップをキーと値のペアを追加したり、キーに値を参照しているディクショナリ。 このクラスは、複数のスレッドまたは同時に共有コンテナーへのアクセス、挿入、または更新する必要があるタスクがある場合に便利です。  
  
 次の例を使用するための基本的な構造を示しています。`concurrent_unordered_map`です。 この例では、['a', ' i'] の範囲内で文字キーを挿入します。 操作の順序が決定しないので、各キーの最終的な値も不定です。 ただし、挿入を実行する、並列でも安全です。  
  
 [!code-cpp[concrt-unordered-map-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_2.cpp)]  
  
 使用する例については`concurrent_unordered_map`、map と reduce を実行操作を並列で、次を参照してください。[する方法: マップの実行と操作を並列に減らす](../../parallel/concrt/how-to-perform-map-and-reduce-operations-in-parallel.md)です。  
  
###  <a name="map-differences"></a> Concurrent_unordered_map 違いと unordered_map  
 `concurrent_unordered_map`クラスとよく似ています、`unordered_map`クラスです。 次の点を示します where`concurrent_unordered_map`異なる`unordered_map`:  
  
-   `erase`、 `bucket`、 `bucket_count`、および`bucket_size`メソッドの名前として`unsafe_erase`、 `unsafe_bucket`、 `unsafe_bucket_count`、および`unsafe_bucket_size`、それぞれします。 `unsafe_`名前付け規則では、これらのメソッドは同時実行セーフではないことを示します。 同時実行セーフの詳細については、次を参照してください。[同時実行セーフな操作](#map-safety)です。  
  
-   既存のポインターまたは反復子、挿入操作は無効になりません。 また、マップに既に存在する項目の順序を変更しないでください。 挿入し、スキャン操作に同時に発生することができます。  
  
-   `concurrent_unordered_map` サポートは、イテレーションのみを転送します。  
  
-   カーソルが無効にしたりによって返される反復子を更新していない`equal_range`です。 カーソルは、範囲の末尾に等しくない項目を追加できます。 Begin 反復子は、同じ項目を指します。  
  
 メソッドが存在しません、デッドロックを回避する`concurrent_unordered_map`メモリ アロケーター、ハッシュ関数、またはその他のユーザー定義のコードを呼び出すときに、ロックを保持します。 また、ハッシュ関数が同じ値に等しいキーを常に評価されたことを確認する必要があります。 最適なハッシュ関数は、ハッシュ コード領域間で一様にキーを配布します。  
  
###  <a name="map-safety"></a> 同時実行セーフな操作  
 `concurrent_unordered_map`クラスには、同時実行セーフの挿入と要素アクセス操作ができるようにします。 挿入操作には、既存のポインターまたは反復子は無効にしないでください。 反復子アクセス、走査の各操作も同時実行セーフです。 次の表は、一般的に使用される`concurrent_unordered_map`メソッドと同時実行セーフである演算子。  
  
|||||  
|-|-|-|-|  
|[at](reference/concurrent-unordered-map-class.md#at)|`count`|`find`|[key_eq](reference/concurrent-unordered-map-class.md#key_eq)|  
|`begin`|`empty`|`get_allocator`|`max_size`|  
|`cbegin`|`end`|`hash_function`|[operator&#91;&#93;](reference/concurrent-unordered-map-class.md#operator_at)|  
|`cend`|`equal_range`|[insert](reference/concurrent-unordered-map-class.md#insert)|`size`|  
  
 ただし、`count`メソッドは同時に実行されているスレッドから安全に呼び出すことが、別のスレッドを場合は、コンテナーに新しい値が挿入される同時に異なる結果が表示されることができます。  
  
 次の表は、一般的に使用されるメソッドと同時実行セーフではない演算子を示します。  
  
||||  
|-|-|-|  
|`clear`|`max_load_factor`|`rehash`|  
|`load_factor`|[operator=](reference/concurrent-unordered-map-class.md#operator_eq) 


  
 これらのメソッドだけでなく任意の方法で始まる`unsafe_`もは同時実行セーフです。  
  
 [[トップ](#top)]  
  
##  <a name="unordered_multimap"></a> concurrent_unordered_multimap クラス  
 [Concurrency::concurrent_unordered_multimap](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)クラスとよく似ています、`concurrent_unordered_map`クラスを同じキーにマップする複数の値を許可する点が異なります。 異なります`concurrent_unordered_map`次のようにします。  
  
-   [Concurrent_unordered_multimap::insert](reference/concurrent-unordered-multimap-class.md#insert)メソッドの代わりに反復子を返します`std::pair<iterator, bool>`です。  

  
-   `concurrent_unordered_multimap`クラスを提供しない`operator[]`も`at`メソッドです。  
  
 次の例を使用するための基本的な構造を示しています。`concurrent_unordered_multimap`です。 この例では、['a', ' i'] の範囲内で文字キーを挿入します。 `concurrent_unordered_multimap` 複数の値を持つキーを使用できます。  
  
 [!code-cpp[concrt-unordered-multimap-structure#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_3.cpp)]  
  
 [[トップ](#top)]  
  
##  <a name="unordered_set"></a> concurrent_unordered_set クラス  
 [Concurrency::concurrent_unordered_set](../../parallel/concrt/reference/concurrent-unordered-set-class.md)クラスとよく似ています、`concurrent_unordered_map`クラスのキーと値のペアではなく値を管理する点が異なります。 `concurrent_unordered_set`クラスを提供しない`operator[]`も`at`メソッドです。  
  
 次の例を使用するための基本的な構造を示しています。`concurrent_unordered_set`です。 この例では、['a', ' i'] の範囲内で文字の値を挿入します。 挿入を実行する、並列でも安全です。  
  
 [!code-cpp[concrt-unordered-set#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_4.cpp)]  
  
 [[トップ](#top)]  
  
##  <a name="unordered_multiset"></a> concurrent_unordered_multiset クラス  
 [Concurrency::concurrent_unordered_multiset](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)クラスとよく似ています、`concurrent_unordered_set`クラスの重複する値を許可する点が異なります。 異なります`concurrent_unordered_set`次のようにします。  
  

-   [Concurrent_unordered_multiset::insert](reference/concurrent-unordered-multiset-class.md#insert)メソッドの代わりに反復子を返します`std::pair<iterator, bool>`です。  

  
-   `concurrent_unordered_multiset`クラスを提供しない`operator[]`も`at`メソッドです。  
  
 次の例を使用するための基本的な構造を示しています。`concurrent_unordered_multiset`です。 この例では、['a', ' i'] の範囲内で文字の値を挿入します。 `concurrent_unordered_multiset` 複数回出現する値を有効にします。  
  
 [!code-cpp[concrt-unordered-multiset#1](../../parallel/concrt/codesnippet/cpp/parallel-containers-and-objects_5.cpp)]  
  
 [[トップ](#top)]  
  
##  <a name="combinable"></a> combinable クラス  
 [Concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラスには、再利用可能なスレッド ローカル ストレージを使用して詳細な計算を実行し、その計算を最終結果にマージが用意されています。 `combinable` オブジェクトは減少変数と考えることができます。  
  
 `combinable`クラスは、いくつかのスレッドまたはタスクの間で共有されているリソースが存在する場合に便利です。 `combinable`クラスを使用して、ロック制御不要の方法で共有リソースへのアクセスを提供することにより共有状態を回避できます。 そのため、このクラスは、複数のスレッドから共有データへのアクセスを同期するためにミュー テックスなど、同期メカニズムを使用する代わりを提供します。  
  
###  <a name="combinable-features"></a> メソッドと機能  
 いくつかの重要なメソッドの次の表は、`combinable`クラスです。 すべての詳細については、`combinable`クラスのメソッドを参照してください[combinable クラス](../../parallel/concrt/reference/combinable-class.md)です。  
  
|メソッド|説明|  
|------------|-----------------|  
|[local](reference/combinable-class.md#local)|現在のスレッド コンテキストに関連付けられているローカル変数への参照を取得します。|  
|[clear](reference/combinable-class.md#clear)|すべてのスレッド ローカル変数を削除、`combinable`オブジェクト。|  
|[combine](reference/combinable-class.md#combine)<br /><br /> [combine_each](reference/combinable-class.md#combine_each)|指定された結合関数を使用すると、すべてのスレッド ローカルの計算のセットから、最終的な値を生成します。|  
  
 `combinable`クラスは、最終的なマージされた結果でパラメーター化されたテンプレート クラス。 既定のコンス トラクターを呼び出す場合は、`T`テンプレート パラメーターの型は、既定のコンス トラクターとコピー コンス トラクターを持つ必要があります。 場合、`T`テンプレート パラメーターの型が既定のコンス トラクターを持たない、初期化関数のパラメーターとして受け取るコンス トラクターのオーバー ロードされたバージョンを呼び出します。  
  
 追加のデータを格納することができます、`combinable`オブジェクトの呼び出し後に、[結合](reference/combinable-class.md#combine)または[combine_each](reference/combinable-class.md#combine_each)メソッドです。 呼び出すことも、`combine`と`combine_each`複数回のメソッドです。 場合にローカルの値はありません、`combinable`オブジェクトに対する変更を`combine`と`combine_each`メソッドは呼び出されるたびに同じ結果を生成します。  
  
###  <a name="combinable-examples"></a> 例  
 例を使用する方法については、`combinable`クラスを次のトピックを参照してください。  
  
-   [方法: combinable を使用してパフォーマンスを向上させる](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
  
-   [方法: combinable を使用して集合を結合する](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
  
 [[トップ](#top)]  
  
## <a name="related-topics"></a>関連トピック  
 [方法: 並列コンテナーを使用して効率を向上させる](../../parallel/concrt/how-to-use-parallel-containers-to-increase-efficiency.md)  
 並列コンテナーを使用して効率的に格納し、並列のデータにアクセスする方法を示します。  
  
 [方法: combinable を使用してパフォーマンスを向上させる](../../parallel/concrt/how-to-use-combinable-to-improve-performance.md)  
 使用する方法を示します、`combinable`クラスの共有の状態を解消して、パフォーマンスが向上します。  
  
 [方法: combinable を使用して集合を結合する](../../parallel/concrt/how-to-use-combinable-to-combine-sets.md)  
 使用する方法を示します、`combine`スレッド ローカル データ セットをマージする関数。  
  
 [並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)  
 スケーラビリティと同時実行アプリケーションを開発するためやすさを促進する命令型プログラミング モデルを提供する PPL について説明します。  
  
## <a name="reference"></a>参照  
 [concurrent_vector クラス](../../parallel/concrt/reference/concurrent-vector-class.md)  
  
 [concurrent_queue クラス](../../parallel/concrt/reference/concurrent-queue-class.md)  
  
 [concurrent_unordered_map クラス](../../parallel/concrt/reference/concurrent-unordered-map-class.md)  
  
 [concurrent_unordered_multimap クラス](../../parallel/concrt/reference/concurrent-unordered-multimap-class.md)  
  
 [concurrent_unordered_set クラス](../../parallel/concrt/reference/concurrent-unordered-set-class.md)  
  
 [concurrent_unordered_multiset クラス](../../parallel/concrt/reference/concurrent-unordered-multiset-class.md)  
  
 [combinable クラス](../../parallel/concrt/reference/combinable-class.md)
