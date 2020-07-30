---
title: concurrent_unordered_map クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- concurrent_unordered_map class
ms.assetid: b2d879dd-87ef-4af9-a266-a5443fd538b8
ms.openlocfilehash: eb2493c3e3303a80c9825620aae0c2ef5270a71a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230338"
---
# <a name="concurrent_unordered_map-class"></a>concurrent_unordered_map クラス

ph x="1" /&gt; クラスは、`std::pair<const K, _Element_type>` 型要素の可変長シーケンスを制御するコンカレンシー セーフなコンテナーです。 このシーケンスは、コンカレンシー セーフな追加、要素アクセス、反復子アクセス、反復子走査の各操作を実行できるように表されます。 ここでは、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化、または特定のトラバーサルの順序の保証ではありません。

## <a name="syntax"></a>構文

```cpp
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

### <a name="parameters"></a>パラメーター

*Kb*<br/>
キーの型。

*_Element_type*<br/>
マップされた型。

*_Hasher*<br/>
ハッシュ関数のオブジェクト型。 この引数は省略可能であり、既定値は `std::hash<K>` です。

*key_equality*<br/>
等価比較関数のオブジェクト型。 この引数は省略可能であり、既定値は `std::equal_to<K>` です。

*_Allocator_type*<br/>
同時実行順序なしのマップのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `std::allocator<std::pair<K` 、 `_Element_type>>` です。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|[説明]|
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

|名前|[説明]|
|----------|-----------------|
|[concurrent_unordered_map](#ctor)|オーバーロードされます。 同時実行順序なしのマップを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[at](#at)|オーバーロードされます。 `concurrent_unordered_map` 内の指定されたキー値を持つ要素を検索します。 このメソッドはコンカレンシー セーフです。|
|[hash_function](#hash_function)|格納されているハッシュ関数オブジェクトを取得します。|
|[insert](#insert)|オーバーロードされます。 要素を `concurrent_unordered_map` オブジェクトに追加します。|
|[key_eq](#key_eq)|格納された等価比較関数のオブジェクトを取得します。|
|[スワップ](#swap)|2 つの `concurrent_unordered_map` オブジェクトのコンテンツを交換します。 このメソッドはコンカレンシー セーフではありません。|
|[unsafe_erase](#unsafe_erase)|オーバーロードされます。 `concurrent_unordered_map` から指定した位置にある要素を削除します。 このメソッドはコンカレンシー セーフではありません。|

### <a name="public-operators"></a>パブリック演算子

|名前|[説明]|
|----------|-----------------|
|[operator\[\]](#operator_at)|オーバーロードされます。 指定したキーを持つ要素を検索または挿入します。 このメソッドはコンカレンシー セーフです。|
|[operator =](#operator_eq)|オーバーロードされます。 別の `concurrent_unordered_map` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドはコンカレンシー セーフではありません。|

## <a name="remarks"></a>解説

クラスの詳細につい `concurrent_unordered_map` ては、「[並列コンテナーとオブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`_Traits`

`_Concurrent_hash`

`concurrent_unordered_map`

## <a name="requirements"></a>必要条件

**ヘッダー:** concurrent_unordered_map

**名前空間:** concurrency

## <a name="at"></a><a name="at"></a>(

`concurrent_unordered_map` 内の指定されたキー値を持つ要素を検索します。 このメソッドはコンカレンシー セーフです。

```cpp
mapped_type& at(const key_type& KVal);

const mapped_type& at(const key_type& KVal) const;
```

### <a name="parameters"></a>パラメーター

*KVal*<br/>
検索するキー値。

### <a name="return-value"></a>戻り値

見つかった要素のデータ値への参照。

### <a name="remarks"></a>解説

引数のキー値が見つからない場合、この関数は、`out_of_range` クラスのオブジェクトをスローします。

## <a name="begin"></a><a name="begin"></a>初め

同時実行コンテナーの最初の要素を指す反復子を返します。 このメソッドはコンカレンシー セーフです。

```cpp
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>戻り値

同時実行コンテナー内の最初の要素を指す反復子。

## <a name="cbegin"></a><a name="cbegin"></a>cbegin

同時実行コンテナーの最初の要素を指す定数反復子を返します。 このメソッドはコンカレンシー セーフです。

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>戻り値

同時実行コンテナー内の最初の要素を指す定数反復子。

## <a name="cend"></a><a name="cend"></a>cend

同時実行コンテナー内の最後の要素の次の位置を指す定数反復子を返します。 このメソッドはコンカレンシー セーフです。

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>戻り値

同時実行コンテナー内の最後の要素の次の位置を指す定数反復子。

## <a name="clear"></a><a name="clear"></a>クリア

同時実行コンテナー内のすべての要素を消去します。 この関数は、同時実行セーフではありません。

```cpp
void clear();
```

## <a name="concurrent_unordered_map"></a><a name="ctor"></a>concurrent_unordered_map

同時実行順序なしのマップを構築します。

```cpp
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

*_Iterator*<br/>
入力反復子の型。

*_Number_of_buckets*<br/>
この順序なしマップのバケットの初期数。

*_Hasher*<br/>
この順序なしのマップのハッシュ関数。

*key_equality*<br/>
この順序なしのマップの等値比較関数。

*_Allocator*<br/>
この順序なしのマップのアロケーター。

*_Begin*<br/>
コピーする要素範囲内の最初の要素の位置。

*_End*<br/>
コピーする要素範囲を超える最初の要素の位置。

*_Umap*<br/>
要素のコピー元または移動元の `concurrent_unordered_map` オブジェクト。

### <a name="remarks"></a>解説

すべてのコンストラクターは、アロケーターオブジェクトを格納 `_Allocator` し、順序なしのマップを初期化します。

最初のコンストラクターは、空の初期マップを指定し、使用するバケット、ハッシュ関数、等値関数、およびアロケーターの種類の数を明示的に指定します。

2番目のコンストラクターは、順序付けられていないマップのアロケーターを指定します。

3番目のコンストラクターは、反復子の範囲 [,) によって指定された値を指定し `_Begin` `_End` ます。

4番目と5番目のコンストラクターは、同時実行順序なしのマップのコピーを指定し `_Umap` ます。

最後のコンストラクターは、同時実行順序なしのマップの移動を指定し `_Umap` ます。

## <a name="count"></a><a name="count"></a>数

指定したキーに一致する要素の数をカウントします。 この関数は、同時実行セーフです。

```cpp
size_type count(const key_type& KVal) const;
```

### <a name="parameters"></a>パラメーター

*KVal*<br/>
検索対象のキー。

### <a name="return-value"></a>戻り値

キーがコンテナー内に出現する回数。

## <a name="empty"></a><a name="empty"></a>指定

要素が存在しないかどうかをテストします。 このメソッドはコンカレンシー セーフです。

```cpp
bool empty() const;
```

### <a name="return-value"></a>戻り値

**`true`** 同時実行コンテナーが空の場合は **`false`** 。それ以外の場合は。

### <a name="remarks"></a>解説

同時挿入が存在する場合、戻り値が読み込まれる前に、同時実行コンテナーが空であるかどうかは、この関数を呼び出した直後に変更される可能性があります。

## <a name="end"></a><a name="end"></a>終わり

同時実行コンテナー内の最後の要素の次の位置を指す反復子を返します。 このメソッドはコンカレンシー セーフです。

```cpp
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>戻り値

同時実行コンテナー内の最後の要素の次の位置を指す反復子。

## <a name="equal_range"></a><a name="equal_range"></a>equal_range

指定されたキーに一致する範囲を検索します。 この関数は、同時実行セーフです。

```cpp
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```

### <a name="parameters"></a>パラメーター

*KVal*<br/>
検索するキー値。

### <a name="return-value"></a>戻り値

最初の要素が先頭の反復子であり、2番目の要素が範囲の末尾を指す反復子である[ペア](../../../standard-library/pair-structure.md)。

### <a name="remarks"></a>解説

同時に挿入を行うと、開始反復子の後、および終了反復子の前に追加のキーが挿入される可能性があります。

## <a name="find"></a><a name="find"></a>探す

指定したキーに一致する要素を検索します。 この関数は、同時実行セーフです。

```cpp
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```

### <a name="parameters"></a>パラメーター

*KVal*<br/>
検索するキー値。

### <a name="return-value"></a>戻り値

指定されたキーと一致した最初の要素の位置を指す反復子 `end()` 。このような要素が存在しない場合は、反復子。

## <a name="get_allocator"></a><a name="get_allocator"></a>get_allocator

この同時実行コンテナーの格納されたアロケーター オブジェクトを返します。 このメソッドはコンカレンシー セーフです。

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>戻り値

この同時実行コンテナーの格納されたアロケーター オブジェクト。

## <a name="hash_function"></a><a name="hash_function"></a>hash_function

格納されているハッシュ関数オブジェクトを取得します。

```cpp
hasher hash_function() const;
```

### <a name="return-value"></a>戻り値

格納されているハッシュ関数オブジェクト。

## <a name="insert"></a><a name="insert"></a>insert

要素を `concurrent_unordered_map` オブジェクトに追加します。

```cpp
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

*_Iterator*<br/>
挿入に使用される反復子の型。

*画像*<br/>
Map に挿入される値の型。

*value*<br/>
挿入する値。

*_Where*<br/>
挿入ポイントを検索する開始位置。

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の末尾。

### <a name="return-value"></a>戻り値

反復子とブール値を含むペア。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>解説

1つ目のメンバー関数は、キーの順序がと同じであるシーケンス内に要素 X が存在するかどうかを判断し `value` ます。 そうでない場合は、このような要素 X を作成し、を使用して初期化し `value` ます。 次に、関数は、X を指定する反復子を決定し `where` ます。挿入が行われた場合、関数はを返し `std::pair(where, true)` ます。 それ以外の場合は `std::pair(where, false)`を返します。

2番目のメンバー関数は、挿入 `value` `_Where` ポイントを検索するために、を被制御シーケンス内で開始位置として使用して、insert () を返します。

3番目のメンバー関数は、範囲 [,) から要素値のシーケンスを挿入し `first` `last` ます。

最後の2つのメンバー関数は、最初の2つのメンバー関数と同じように動作し `value` ますが、が挿入された値を構築するために使用される点が異なります。

## <a name="key_eq"></a><a name="key_eq"></a>key_eq

格納された等価比較関数のオブジェクトを取得します。

```cpp
key_equal key_eq() const;
```

### <a name="return-value"></a>戻り値

格納された等価比較関数のオブジェクト。

## <a name="load_factor"></a><a name="load_factor"></a>load_factor

コンテナーの現在の占有率を計算して返します。 占有率は、コンテナー内の要素の数をバケット数で割った値です。

```cpp
float load_factor() const;
```

### <a name="return-value"></a>戻り値

コンテナーの占有率。

## <a name="max_load_factor"></a><a name="max_load_factor"></a>max_load_factor

コンテナーの最大占有率を取得または設定します。 最大の占有率は、コンテナーが内部テーブルを拡張する前に、どのバケットにも含まれる要素の最大数です。

```cpp
float max_load_factor() const;

void max_load_factor(float _Newmax);
```

### <a name="parameters"></a>パラメーター

`_Newmax`

### <a name="return-value"></a>戻り値

1 つ目のメンバー関数は、格納されている最大テーブル占有率を返します。 2番目のメンバー関数は値を返しませんが、指定されたテーブル占有率が無効である場合は[out_of_range](../../../standard-library/out-of-range-class.md)例外をスローします。

## <a name="max_size"></a><a name="max_size"></a>max_size

アロケーターによって決定される同時実行コンテナーの最大サイズを返します。 このメソッドはコンカレンシー セーフです。

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>戻り値

この同時実行コンテナーに挿入できる要素の最大数。

### <a name="remarks"></a>解説

この上限値は、実際にコンテナーが保持できるものよりも大きくなる場合があります。

## <a name="operator"></a><a name="operator_at"></a>演算子 []

指定したキーを持つ要素を検索または挿入します。 このメソッドはコンカレンシー セーフです。

```cpp
mapped_type& operator[](const key_type& kval);

mapped_type& operator[](key_type&& kval);
```

### <a name="parameters"></a>パラメーター

*KVal*<br/>
のキー値

検索または挿入します。

### <a name="return-value"></a>戻り値

検出または挿入された要素のデータ値への参照。

### <a name="remarks"></a>解説

引数のキー値が見つからない場合は、データ型の既定値と一緒に挿入されます。

`operator[]`はを使用してマップに要素を挿入するために使用でき `m` `m[key] = DataValue;` `DataValue` `mapped_type` ます。は、キー値がである要素のの値です `key` 。

`operator[]` を使用して要素を挿入した場合、返される参照では、挿入によって既存の要素が変更される、または新しい要素が作成されるかどうかは指示されません。 メンバー関数 `find` と[挿入](#insert)を使用して、指定したキーを持つ要素が挿入前に既に存在するかどうかを判断できます。

## <a name="operator"></a><a name="operator_eq"></a>operator =

別の `concurrent_unordered_map` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドはコンカレンシー セーフではありません。

```cpp
concurrent_unordered_map& operator= (const concurrent_unordered_map& _Umap);

concurrent_unordered_map& operator= (concurrent_unordered_map&& _Umap);
```

### <a name="parameters"></a>パラメーター

*_Umap*<br/>
ソース `concurrent_unordered_map` オブジェクト。

### <a name="return-value"></a>戻り値

この `concurrent_unordered_map` オブジェクトへの参照。

### <a name="remarks"></a>解説

同時実行ベクターで既存の要素を消去した後、は `operator=` の内容を `_Umap` 同時実行ベクターにコピーまたは移動します。

## <a name="rehash"></a><a name="rehash"></a>rehash

ハッシュ テーブルをリビルドします。

```cpp
void rehash(size_type _Buckets);
```

### <a name="parameters"></a>パラメーター

*_Buckets*<br/>
必要なバケット数。

### <a name="remarks"></a>解説

メンバー関数は、バケット数を `_Buckets` 以上に変更し、必要に応じて、ハッシュ テーブルをリビルドします。 バケットの数は2の累乗でなければなりません。 2の累乗でない場合は、次に大きい2の累乗に切り上げられます。

バケットの数が無効である場合 (0 またはバケットの最大数を超える)、 [out_of_range](../../../standard-library/out-of-range-class.md)例外がスローされます。

## <a name="size"></a><a name="size"></a>幅

この同時実行コンテナー内の要素の数を返します。 このメソッドはコンカレンシー セーフです。

```cpp
size_type size() const;
```

### <a name="return-value"></a>戻り値

コンテナー内の項目の数。

### <a name="remarks"></a>解説

同時挿入が存在する場合、戻り値が読み込まれる前に、同時実行コンテナー内の要素の数が、この関数を呼び出した直後に変更される可能性があります。

## <a name="swap"></a><a name="swap"></a>フォト

2 つの `concurrent_unordered_map` オブジェクトのコンテンツを交換します。 このメソッドはコンカレンシー セーフではありません。

```cpp
void swap(concurrent_unordered_map& _Umap);
```

### <a name="parameters"></a>パラメーター

*_Umap*<br/>
`concurrent_unordered_map`交換するオブジェクト。

## <a name="unsafe_begin"></a><a name="unsafe_begin"></a>unsafe_begin

特定のバケットのこのコンテナー内の最初の要素を指す反復子を返します。

```cpp
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
バケットインデックス。

### <a name="return-value"></a>戻り値

バケットの先頭を指す反復子。

## <a name="unsafe_bucket"></a><a name="unsafe_bucket"></a>unsafe_bucket

このコンテナー内の特定のキーがマップされるバケットインデックスを返します。

```cpp
size_type unsafe_bucket(const key_type& KVal) const;
```

### <a name="parameters"></a>パラメーター

*KVal*<br/>
検索対象の要素キー。

### <a name="return-value"></a>戻り値

このコンテナー内のキーのバケットインデックス。

## <a name="unsafe_bucket_count"></a><a name="unsafe_bucket_count"></a>unsafe_bucket_count

このコンテナー内の現在のバケット数を返します。

```cpp
size_type unsafe_bucket_count() const;
```

### <a name="return-value"></a>戻り値

このコンテナー内の現在のバケット数。

## <a name="unsafe_bucket_size"></a><a name="unsafe_bucket_size"></a>unsafe_bucket_size

このコンテナーの特定のバケットに含まれる項目の数を返します。

```cpp
size_type unsafe_bucket_size(size_type _Bucket);
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
検索対象のバケット。

### <a name="return-value"></a>戻り値

このコンテナー内の現在のバケット数。

## <a name="unsafe_cbegin"></a><a name="unsafe_cbegin"></a>unsafe_cbegin

特定のバケットのこのコンテナー内の最初の要素を指す反復子を返します。

```cpp
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
バケットインデックス。

### <a name="return-value"></a>戻り値

バケットの先頭を指す反復子。

## <a name="unsafe_cend"></a><a name="unsafe_cend"></a>unsafe_cend

特定のバケット内の最後の要素の次の位置を指す反復子を返します。

```cpp
const_local_iterator unsafe_cend(size_type _Bucket) const;
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
バケットインデックス。

### <a name="return-value"></a>戻り値

バケットの先頭を指す反復子。

## <a name="unsafe_end"></a><a name="unsafe_end"></a>unsafe_end

特定のバケットのこのコンテナー内の最後の要素を指す反復子を返します。

```cpp
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
バケットインデックス。

### <a name="return-value"></a>戻り値

バケットの末尾を指す反復子。

## <a name="unsafe_erase"></a><a name="unsafe_erase"></a>unsafe_erase

`concurrent_unordered_map` から指定した位置にある要素を削除します。 このメソッドはコンカレンシー セーフではありません。

```cpp
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator _Begin,
    const_iterator _End);

size_type unsafe_erase(
    const key_type& KVal);
```

### <a name="parameters"></a>パラメーター

*_Where*<br/>
消去する反復子の位置。

*_Begin*<br/>
消去する要素範囲内の最初の要素の位置。

*_End*<br/>
消去する要素の範囲を超える最初の要素の位置。

*KVal*<br/>
消去するキー値。

### <a name="return-value"></a>戻り値

最初の 2 つのメンバー関数は、削除された要素の後の最初の残存要素を指定する反復子を返します。このような要素が存在しない場合は、`concurrent_unordered_map::end`() が返されます。 3 つ目のメンバー関数は削除する要素の数を返します。

### <a name="remarks"></a>解説

1つ目のメンバー関数は、が指す被制御シーケンスの要素を削除し `_Where` ます。 2番目のメンバー関数は、範囲 [,) 内の要素を削除し `_Begin` `_End` ます。

3番目のメンバー関数は、(kval) で区切られた範囲内の要素を削除し `concurrent_unordered_map::equal_range` ます。

## <a name="unsafe_max_bucket_count"></a><a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count

このコンテナー内のバケットの最大数を返します。

```cpp
size_type unsafe_max_bucket_count() const;
```

### <a name="return-value"></a>戻り値

このコンテナー内のバケットの最大数。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)
