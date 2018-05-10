---
title: concurrent_unordered_map クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::concurrent_unordered_map
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::at
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::hash_function
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::insert
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::key_eq
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::swap
- CONCURRENT_UNORDERED_MAP/concurrency::concurrent_unordered_map::unsafe_erase
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_map class
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 932cfe232b07a9020af450ad33bb34101827ac79
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="concurrentunorderedmap-class"></a>concurrent_unordered_map クラス
`concurrent_unordered_map` クラスは、`std::pair<const K, _Element_type>` 型要素の可変長シーケンスを制御する同時実行セーフなコンテナーです。 このシーケンスは、同時実行セーフな追加、要素アクセス、反復子アクセス、反復子走査の各操作を実行できるように表されます。  
  
## <a name="syntax"></a>構文  
  
```
template <typename K,
    typename _Element_type,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>
>,
 typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<std::pair<const K,
    _Element_type>>> class concurrent_unordered_map : public details::_Concurrent_hash<details::_Concurrent_unordered_map_traits<K,
    _Element_type,
 details::_Hash_compare<K,
    _Hasher,
 key_equality>,
    _Allocator_type,
 false>>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `K`  
 キーの型。  
  
 `_Element_type`  
 マップされた型。  
  
 `_Hasher`  
 ハッシュ関数のオブジェクト型。 この引数は省略可能であり、既定値は `std::hash<K>` です。  
  
 `key_equality`  
 等価比較関数のオブジェクト型。 この引数は省略可能であり、既定値は `std::equal_to<K>` です。  
  
 `_Allocator_type`  
 同時実行順序なしのマップのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。 この引数は省略可能、既定値は`std::allocator<std::pair<K`、`_Element_type>>`です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`allocator_type`|ストレージを管理するためのアロケーターの型です。|  
|`const_iterator`|被制御シーケンスの定数反復子の型です。|  
|`const_local_iterator`|被制御シーケンスの定数バケット反復子の型です。|  
|`const_pointer`|要素への定数ポインターの型です。|  
|`const_reference`|要素への定数参照の型です。|  
|`difference_type`|2 つの要素間の距離を表す、符号付きの型です。|  
|`hasher`|ハッシュ関数の型です。|  
|`iterator`|被制御シーケンスの反復子の型です。|  
|`key_equal`|比較関数の型です。|  
|`key_type`|順序付けキーの型です。|  
|`local_iterator`|被制御シーケンスのバケット反復子の型です。|  
|`mapped_type`|各キーに関連付けられた、マップされた値の型です。|  
|`pointer`|要素へのポインターの型です。|  
|`reference`|要素への参照の型です。|  
|`size_type`|2 つの要素間の距離を表す、符号なしの型です。|  
|`value_type`|要素の型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[concurrent_unordered_map](#ctor)|オーバーロードされます。 同時実行順序なしのマップを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[at](#at)|オーバーロードされます。 `concurrent_unordered_map` 内の指定されたキー値を持つ要素を検索します。 このメソッドは同時実行セーフです。|  
|[hash_function](#hash_function)|格納されているハッシュ関数オブジェクトを取得します。|  
|[insert](#insert)|オーバーロードされます。 要素を `concurrent_unordered_map` オブジェクトに追加します。|  
|[key_eq](#key_eq)|格納された等価比較関数のオブジェクトを取得します。|  
|[swap](#swap)|2 つの `concurrent_unordered_map` オブジェクトのコンテンツを交換します。 このメソッドは同時実行セーフではありません。|  
|[unsafe_erase](#unsafe_erase)|オーバーロードされます。 `concurrent_unordered_map` から指定した位置にある要素を削除します。 このメソッドは同時実行セーフではありません。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator[]](#operator_at)|オーバーロードされます。 指定したキーを持つ要素を検索または挿入します。 このメソッドは同時実行セーフです。|  
|[operator=](#operator_eq)|オーバーロードされます。 別の `concurrent_unordered_map` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。|  
  
## <a name="remarks"></a>コメント  
 詳細については、`concurrent_unordered_map`クラスを参照してください[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_map`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concurrent_unordered_map.h  
  
 **名前空間:** concurrency  
  
##  <a name="at"></a> で 

 `concurrent_unordered_map` 内の指定されたキー値を持つ要素を検索します。 このメソッドは同時実行セーフです。  
  
```
mapped_type& at(const key_type& KVal);

const mapped_type& at(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 検索するキー値。  
  
### <a name="return-value"></a>戻り値  
 見つかった要素のデータ値への参照。  
  
### <a name="remarks"></a>コメント  
 引数のキー値が見つからない場合、この関数は、`out_of_range` クラスのオブジェクトをスローします。  
  
##  <a name="begin"></a> 開始 

 同時実行コンテナーの最初の要素を指す反復子を返します。 このメソッドは同時実行セーフです。  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行コンテナーの最初の要素の反復子。  
  
##  <a name="cbegin"></a> cbegin 

 同時実行コンテナーの最初の要素を指す定数反復子を返します。 このメソッドは同時実行セーフです。  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行コンテナーの最初の要素に定数反復子。  
  
##  <a name="cend"></a> cend 

 同時実行コンテナーの最後の要素の次の場所を指す定数反復子を返します。 このメソッドは同時実行セーフです。  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>戻り値  
 位置を同時実行コンテナーの最後の要素を指す定数反復子。  
  
##  <a name="clear"></a> オフ 

 同時実行コンテナー内のすべての要素を消去します。 この関数は、同時実行セーフではありません。  
  
```
void clear();
```  
  
##  <a name="ctor"></a> concurrent_unordered_map 

 同時実行順序なしのマップを構築します。  
  
```
explicit concurrent_unordered_map(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_map(_Iterator _Begin,
    _Iterator _End,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap);

concurrent_unordered_map(
    const concurrent_unordered_map& _Umap,
    const allocator_type& _Allocator);

concurrent_unordered_map(
    concurrent_unordered_map&& _Umap);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 入力反復子の型。  
  
 `_Number_of_buckets`  
 この順序なしのマップのバケットの初期数。  
  
 `_Hasher`  
 この順序なしのマップのハッシュ関数です。  
  
 `key_equality`  
 この順序なしのマップに対して等値比較関数。  
  
 `_Allocator`  
 この順序なしのマップのアロケーター。  
  
 `_Begin`  
 コピーする要素範囲内の最初の要素の位置。  
  
 `_End`  
 コピーする要素範囲を超える最初の要素の位置。  
  
 `_Umap`  
 要素のコピー元または移動元の `concurrent_unordered_map` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 すべてのコンス トラクターは、アロケーター オブジェクトを格納`_Allocator`と順序なしのマップを初期化します。  
  
 最初のコンス トラクターは、空の初期マップおよび明示的を指定、バケット数ハッシュ関数、等値関数と allocator の型を使用します。  
  
 2 番目のコンス トラクターは、順序なしのマップのアロケーターを指定します。  
  
 3 番目のコンス トラクターは、反復子の範囲で指定された値を指定する [ `_Begin`、 `_End`)。  
  
 4 番目と 5 番目のコンス トラクターは、同時実行順序なしのマップのコピーを指定`_Umap`です。  
  
 最後のコンス トラクターは、同時実行順序なしのマップの移動を指定`_Umap`です。  
  
##  <a name="count"></a> カウント 

 指定したキーに一致する要素の数をカウントします。 この関数は、同時実行セーフです。  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 検索対象のキー。  
  
### <a name="return-value"></a>戻り値  
 コンテナーにキーが表示される回数を超えるを回数です。  
  
##  <a name="empty"></a> 空 

 要素が存在しないかどうかをテストします。 このメソッドは同時実行セーフです。  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true` 同時実行コンテナーが空の場合、`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 同時実行の挿入が存在する場合、同時実行コンテナーが空かどうかは、戻り値があっても読み取る前に、この関数の呼び出し後すぐに変更できます。  
  
##  <a name="end"></a> 終わり 

 同時実行コンテナーの最後の要素の次の場所を指す反復子を返します。 このメソッドは同時実行セーフです。  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>戻り値  
 位置を同時実行コンテナーの最後の要素を指す反復子。  
  
##  <a name="equal_range"></a> equal_range 

 指定したキーに一致する範囲を検索します。 この関数は、同時実行セーフです。  
  
```
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 検索するキー値。  
  
### <a name="return-value"></a>戻り値  
 A[ペア](http://msdn.microsoft.com/en-us/c5a37023-d939-4eb2-ae24-ce8e0cd4505d)ここでは先頭を指す反復子の最初の要素と 2 番目の要素は、範囲の終了日を指す反復子。  
  
### <a name="remarks"></a>コメント  
 同時実行の挿入開始反復子の後と、終了反復子の前に挿入される追加のキーが発生することができます。  
  
##  <a name="find"></a> 検索 

 指定したキーに一致する要素を検索します。 この関数は、同時実行セーフです。  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 検索するキー値。  
  
### <a name="return-value"></a>戻り値  
 場所を指す反復子の指定されたキーに一致する最初の要素または反復子`end()`このような要素が存在しない場合。  
  
##  <a name="get_allocator"></a> get_allocator 

 この同時実行コンテナーの格納されたアロケーター オブジェクトを返します。 このメソッドは同時実行セーフです。  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>戻り値  
 この同時実行コンテナーの格納されたアロケーター オブジェクト。  
  
##  <a name="hash_function"></a> hash_function 

 格納されているハッシュ関数オブジェクトを取得します。  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>戻り値  
 格納されているハッシュ関数オブジェクト。  
  
##  <a name="insert"></a> 挿入します。 

 要素を `concurrent_unordered_map` オブジェクトに追加します。  
  
```
std::pair<iterator,
    bool> insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
std::pair<iterator,
    bool> insert(
    V&& value);

template<class V>
typename std::enable_if<!std::is_same<const_iterator,
    typename std::remove_reference<V>::type>::value,
    iterator>::type insert(
    const_iterator _Where,
    V&& value);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 反復子の型を挿入するために使用します。  
  
 `V`  
 マップに挿入された値の型。  
  
 `value`  
 挿入する値。  
  
 `_Where`  
 挿入ポイントを検索する開始位置。  
  
 `first`  
 挿入する範囲の先頭。  
  
 `last`  
 挿入する範囲の終了。  
  
### <a name="return-value"></a>戻り値  
 反復子とブール値を含むペア。 詳細については「解説」セクションを参照してください。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数は、シーケンス キーを持ついるのと同じ順序で要素 X が存在するかどうかを判断`value`です。 場合は、このような要素 X を作成しで初期化されて`value`です。 関数が、反復子を決定し、 `where` X を指定します。挿入が発生したかどうか、関数を返します`std::pair(where, true)`です。 返しますそれ以外の場合、`std::pair(where, false)`です。  
  
 2 番目のメンバー関数は、挿入を返します ( `value`) を使用して、`_Where`挿入ポイントを検索する被制御シーケンス内での第一歩として。  
  
 3 番目のメンバー関数は、範囲から要素の値のシーケンスを挿入します。 [ `first`、 `last`)。  
  
 最後の 2 つのメンバー関数の動作は点を除いて、最初の 2 つと同じ`value`挿入する値を構築するために使用します。  
  
##  <a name="key_eq"></a> key_eq 

 格納された等価比較関数のオブジェクトを取得します。  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>戻り値  
 格納された等価比較関数のオブジェクト。  
  
##  <a name="load_factor"></a> load_factor 

 計算し、コンテナーの現在の占有率を返します。 占有率は、バケットの数で割った、コンテナー内の要素の数です。  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>戻り値  
 コンテナーの占有率。  
  
##  <a name="max_load_factor"></a> max_load_factor 

 取得またはコンテナーの最大テーブル占有率を設定します。 最大テーブル占有率は、コンテナーは、内部テーブルを拡張する前にバケットに含まするよりも要素の最大数です。  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Newmax`  
  
### <a name="return-value"></a>戻り値  
 1 つ目のメンバー関数は、格納されている最大テーブル占有率を返します。 2 番目のメンバー関数は、値を返さないが、スロー、 [out_of_range](../../../standard-library/out-of-range-class.md)例外の場合は、指定された占有率が有効ではありません.  
  
##  <a name="max_size"></a> max_size 

 アロケーターによって決定される、同時実行コンテナーの最大サイズを返します。 このメソッドは同時実行セーフです。  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>戻り値  
 この同時実行コンテナーに挿入できる要素の最大数。  
  
### <a name="remarks"></a>コメント  
 この上限値実際にどのようなコンテナー実際に保持できるよりも高い場合があります。  
  
##  <a name="operator_at"></a> operator[] 

 指定したキーを持つ要素を検索または挿入します。 このメソッドは同時実行セーフです。  
  
```
mapped_type& operator[](const key_type& kval);

mapped_type& operator[](key_type&& kval);
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 キー値  
  
 検索または挿入します。  
  
### <a name="return-value"></a>戻り値  
 見つからないか、または挿入される要素のデータ値への参照。  
  
### <a name="remarks"></a>コメント  
 引数のキー値が見つからない場合は、データ型の既定値と一緒に挿入されます。  
  
 `operator[]` 要素を挿入する、マップに使用する場合があります`m`を使用して`m[key] = DataValue;`ここで、`DataValue`の値は、`mapped_type`のキーの値を持つ要素の`key`します。  
  
 `operator[]` を使用して要素を挿入した場合、返される参照では、挿入によって既存の要素が変更される、または新しい要素が作成されるかどうかは指示されません。 メンバー関数は、`find`と[挿入](#insert)指定したキーを持つ要素が、挿入前に既にかどうかを判断するために使用できます。  
  
##  <a name="operator_eq"></a> 演算子 = 

 別の `concurrent_unordered_map` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。  
  
```
concurrent_unordered_map& operator= (const concurrent_unordered_map& _Umap);

concurrent_unordered_map& operator= (concurrent_unordered_map&& _Umap);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Umap`  
 ソース `concurrent_unordered_map` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `concurrent_unordered_map` オブジェクトへの参照。  
  
### <a name="remarks"></a>コメント  
 既存の要素の同時実行ベクターを消去した後`operator=`コピーまたは移動の内容`_Umap`同時実行ベクターにします。  
  
##  <a name="rehash"></a> rehash 

 ハッシュ テーブルをリビルドします。  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Buckets`  
 目的のバケットの数。  
  
### <a name="remarks"></a>コメント  
 メンバー関数は、バケット数を `_Buckets` 以上に変更し、必要に応じて、ハッシュ テーブルをリビルドします。 バケット数は 2 の累乗である必要があります。 場合いない 2 の累乗で、最も近い 2 の累乗に切り上げられますされます。  
  
 スロー、 [out_of_range](../../../standard-library/out-of-range-class.md)例外バケットの数が有効な場合 (0 またはバケットの最大数より大きい)。  
  
##  <a name="size"></a> サイズ 

 この同時実行コンテナーの要素の数を返します。 このメソッドは同時実行セーフです。  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 コンテナー内の項目の数。  
  
### <a name="remarks"></a>コメント  
 同時実行の挿入が存在する場合は、同時実行コンテナー内の要素の数を戻り値があっても読み取る前に、この関数の呼び出し後すぐに変更できます。  
  
##  <a name="swap"></a> スワップ 

 2 つの `concurrent_unordered_map` オブジェクトのコンテンツを交換します。 このメソッドは同時実行セーフではありません。  
  
```
void swap(concurrent_unordered_map& _Umap);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Umap`  
 `concurrent_unordered_map`交換するオブジェクト。  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 特定のバケットのこのコンテナー内の最初の要素を反復子を返します。  
  
```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 バケットのインデックス。  
  
### <a name="return-value"></a>戻り値  
 バケットの先頭を指す反復子。  
  
##  <a name="unsafe_bucket"></a> unsafe_bucket 

 このコンテナー内に特定のキーがマップされるバケットのインデックスを返します。  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `KVal`  
 検索対象の要素キー。  
  
### <a name="return-value"></a>戻り値  
 このコンテナー内のキーのバケットのインデックス。  
  
##  <a name="unsafe_bucket_count"></a> unsafe_bucket_count 

 このコンテナー内の現在のバケット数を返します。  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>戻り値  
 現在、このコンテナー内のバケットの数。  
  
##  <a name="unsafe_bucket_size"></a> unsafe_bucket_size 

 このコンテナーの特定のバケット内の項目数を返します。  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 検索するバケット。  
  
### <a name="return-value"></a>戻り値  
 現在、このコンテナー内のバケットの数。  
  
##  <a name="unsafe_cbegin"></a> unsafe_cbegin 

 特定のバケットのこのコンテナー内の最初の要素を反復子を返します。  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 バケットのインデックス。  
  
### <a name="return-value"></a>戻り値  
 バケットの先頭を指す反復子。  
  
##  <a name="unsafe_cend"></a> unsafe_cend 

 位置を特定のバケットの最後の要素を指す反復子を返します。  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 バケットのインデックス。  
  
### <a name="return-value"></a>戻り値  
 バケットの先頭を指す反復子。  
  
##  <a name="unsafe_end"></a> unsafe_end 

 特定のバケットには、このコンテナー内の最後の要素を反復子を返します。  
  
```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Bucket`  
 バケットのインデックス。  
  
### <a name="return-value"></a>戻り値  
 バケットの末尾を指す反復子。  
  
##  <a name="unsafe_erase"></a> unsafe_erase 

 `concurrent_unordered_map` から指定した位置にある要素を削除します。 このメソッドは同時実行セーフではありません。  
  
```
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator _Begin,
    const_iterator _End);

size_type unsafe_erase(
    const key_type& KVal);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Where`  
 消去する反復子の位置。  
  
 `_Begin`  
 消去する要素の範囲内の最初の要素の位置。  
  
 `_End`  
 消去する要素の範囲を超える最初の要素の位置。  
  
 `KVal`  
 消去するキー値。  
  
### <a name="return-value"></a>戻り値  
 最初の 2 つのメンバー関数は、削除された要素の後の最初の残存要素を指定する反復子を返します。このような要素が存在しない場合は、`concurrent_unordered_map::end`() が返されます。 3 つ目のメンバー関数は削除する要素の数を返します。  
  
### <a name="remarks"></a>コメント  
 最初のメンバー関数によって示される、被制御シーケンスの要素を削除する`_Where`です。 2 番目のメンバー関数は、範囲内の要素を削除 [ `_Begin`、 `_End`)。  
  
 3 番目のメンバー関数で区切られた範囲内の要素を削除する`concurrent_unordered_map::equal_range`(KVal)。  
  
##  <a name="unsafe_max_bucket_count"></a> unsafe_max_bucket_count 

 このコンテナー内には、バケットの最大数を返します。  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>戻り値  
 このコンテナー内のバケットの最大数。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)



