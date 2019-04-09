---
title: concurrent_unordered_set クラス
ms.date: 11/04/2016
f1_keywords:
- concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::concurrent_unordered_set
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::hash_function
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::insert
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::key_eq
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::swap
- CONCURRENT_UNORDERED_SET/concurrency::concurrent_unordered_set::unsafe_erase
helpviewer_keywords:
- concurrent_unordered_set class
ms.assetid: c61f9a9a-4fd9-491a-9251-e300737ecf4b
ms.openlocfilehash: 43bce15f001e0daee817d9dae345b5d0858f2baa
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57286206"
---
# <a name="concurrentunorderedset-class"></a>concurrent_unordered_set クラス

`concurrent_unordered_set`クラスは、同時実行セーフなコンテナー K. 型の要素の可変長シーケンスを制御します。により、同時実行セーフな方法で、シーケンスが表される要素へのアクセス、反復子アクセス、および反復子走査の各操作を追加します。

## <a name="syntax"></a>構文

```
template <typename K,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>
>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>> class concurrent_unordered_set : public details::_Concurrent_hash<details::_Concurrent_unordered_set_traits<K,
    details::_Hash_compare<K,
_Hasher,
    key_equality>,
_Allocator_type,
    false>>;
```

#### <a name="parameters"></a>パラメーター

*K*<br/>
キーの型。

*_Hasher*<br/>
ハッシュ関数のオブジェクト型。 この引数は省略可能であり、既定値は `std::hash<K>` です。

*key_equality*<br/>
等価比較関数のオブジェクト型。 この引数は省略可能であり、既定値は `std::equal_to<K>` です。

*_Allocator_type*<br/>
同時実行順序なしのセットのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `std::allocator<K>` です。

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
|`pointer`|要素へのポインターの型です。|
|`reference`|要素への参照の型です。|
|`size_type`|2 つの要素間の距離を表す、符号なしの型です。|
|`value_type`|要素の型。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[concurrent_unordered_set](#ctor)|オーバーロードされます。 同時実行順序なしのセットを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[hash_function](#hash_function)|格納されているハッシュ関数オブジェクトを返します。|
|[insert](#insert)|オーバーロードされます。 要素を `concurrent_unordered_set` オブジェクトに追加します。|
|[key_eq](#key_eq)|格納された等価比較関数のオブジェクトを返します。|
|[swap](#swap)|2 つの `concurrent_unordered_set` オブジェクトのコンテンツを交換します。 このメソッドはコンカレンシー セーフではありません。|
|[unsafe_erase](#unsafe_erase)|オーバーロードされます。 `concurrent_unordered_set` から指定した位置にある要素を削除します。 このメソッドはコンカレンシー セーフではありません。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator=](#operator_eq)|オーバーロードされます。 別の `concurrent_unordered_set` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドはコンカレンシー セーフではありません。|

## <a name="remarks"></a>Remarks

詳細については、`concurrent_unordered_set`クラスを参照してください[並列コンテナーとオブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`_Traits`

`_Concurrent_hash`

`concurrent_unordered_set`

## <a name="requirements"></a>必要条件

**ヘッダー:** concurrent_unordered_set.h

**名前空間:** concurrency

##  <a name="begin"></a> 開始

同時実行コンテナーの最初の要素を指す反復子を返します。 このメソッドはコンカレンシー セーフです。

```
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>戻り値

同時実行コンテナーの最初の要素の反復子。

##  <a name="cbegin"></a> cbegin

同時実行コンテナーの最初の要素を指す定数反復子を返します。 このメソッドはコンカレンシー セーフです。

```
const_iterator cbegin() const;
```

### <a name="return-value"></a>戻り値

同時実行コンテナーの最初の要素に定数反復子。

##  <a name="cend"></a> cend

同時実行コンテナーの最後の要素の次の位置を指す定数反復子を返します。 このメソッドはコンカレンシー セーフです。

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

##  <a name="ctor"></a> concurrent_unordered_set

同時実行順序なしのセットを構築します。

```
explicit concurrent_unordered_set(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_set(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_set(_Iterator first,
    _Iterator last,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_set(
    const concurrent_unordered_set& _Uset);

concurrent_unordered_set(
    const concurrent_unordered_set& _Uset,
    const allocator_type& _Allocator);

concurrent_unordered_set(
    concurrent_unordered_set&& _Uset);
```

### <a name="parameters"></a>パラメーター

*_Iterator*<br/>
入力反復子の型。

*_Number_of_buckets*<br/>
この順序付けられていないセットのバケットの初期数。

*_Hasher*<br/>
この順序付けられていないセットのハッシュ関数。

*key_equality*<br/>
この順序なしのセットに対して等値比較関数。

*_Allocator*<br/>
この順序付けられていないセットのアロケーター。

*first*<br/>
*last*<br/>
*_Uset*<br/>
要素のコピー元または移動元の `concurrent_unordered_set` オブジェクト。

### <a name="remarks"></a>Remarks

すべてのコンス トラクターは、アロケーター オブジェクトを格納`_Allocator`と順序なしのセットを初期化します。

最初のコンス トラクター空の初期セットを指定しますを明示的に指定します、バケット数ハッシュ関数、等しいかどうかの関数とアロケーターの型を使用します。

2 番目のコンス トラクターでは、順序なしのセットのアロケーターを指定します。

3 番目のコンス トラクターは、反復子の範囲で指定された値を指定する [ `_Begin`、 `_End`)。

4 番目と 5 番目のコンス トラクターは、同時実行の順序付けられていないセットのコピーを指定します。`_Uset`します。

最後のコンス トラクターは、同時実行の順序付けられていないセットの移動を指定`_Uset`します。

##  <a name="count"></a> カウント

指定したキーに一致する要素の数をカウントします。 この関数は、同時実行セーフです。

```
size_type count(const key_type& KVal) const;
```

### <a name="parameters"></a>パラメーター

*KVal*<br/>
検索対象のキー。

### <a name="return-value"></a>戻り値

コンテナーにキーが表示される回数の合計を回数します。

##  <a name="empty"></a> 空

要素が存在しないかどうかをテストします。 このメソッドはコンカレンシー セーフです。

```
bool empty() const;
```

### <a name="return-value"></a>戻り値

**true**同時実行コンテナーが空の場合**false**それ以外の場合。

### <a name="remarks"></a>Remarks

同時実行の挿入がある場合、同時実行コンテナーが空かどうかを戻り値は読み取り専用でも前に、この関数の呼び出し直後後変更可能性があります。

##  <a name="end"></a> 終わり

同時実行コンテナーの最後の要素の次の位置を指す反復子を返します。 このメソッドはコンカレンシー セーフです。

```
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>戻り値

同時実行コンテナーの最後の要素を指す反復子。

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

*KVal*<br/>
検索するキー値。

### <a name="return-value"></a>戻り値

A[ペア](../../../standard-library/pair-structure.md)最初の要素は、反復子を先頭に、2 番目の要素が、範囲の末尾に反復子です。

### <a name="remarks"></a>Remarks

同時実行の挿入を begin 反復子の後と終わりの反復子の前に挿入される追加のキーが発生することができます。

##  <a name="find"></a> 検索

指定したキーに一致する要素を検索します。 この関数は、同時実行セーフです。

```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```

### <a name="parameters"></a>パラメーター

*KVal*<br/>
検索するキー値。

### <a name="return-value"></a>戻り値

指定したキーに一致する最初の要素の位置を指す反復子または反復子`end()`そのような要素が存在しない場合。

##  <a name="get_allocator"></a> get_allocator

この同時実行コンテナーの格納されたアロケーター オブジェクトを返します。 このメソッドはコンカレンシー セーフです。

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>戻り値

この同時実行コンテナーの格納されたアロケーター オブジェクト。

##  <a name="hash_function"></a> hash_function

格納されているハッシュ関数オブジェクトを返します。

```
hasher hash_function() const;
```

### <a name="return-value"></a>戻り値

格納されているハッシュ関数オブジェクト。

##  <a name="insert"></a> 挿入します。

要素を `concurrent_unordered_set` オブジェクトに追加します。

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

*_Iterator*<br/>
反復子の型を挿入するために使用します。

*V*<br/>
セットに挿入された値の型。

*value*<br/>
挿入する値。

*_Where*<br/>
挿入ポイントを検索する開始位置。

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の終了。

### <a name="return-value"></a>戻り値

反復子とブール値を含むペア。 詳細については、「解説」を参照してください。

### <a name="remarks"></a>Remarks

最初のメンバー関数は、要素 X がのと同じ順序付けキーを持つが、シーケンス内に存在するかどうかを決定します。`value`します。 場合は、このような要素 X を作成して初期化で`value`します。 関数は、反復子を決定し、 `where` X を指定します。挿入が発生したかどうか、関数を返します`std::pair(where, true)`します。 それ以外の場合は、 `std::pair(where, false)`を返します。

2 番目のメンバー関数は、挿入を返します ( `value`) を使用して、`_Where`として挿入ポイントを検索する被制御シーケンス内の開始場所。

3 番目のメンバー関数は、範囲からの要素の値のシーケンスを挿入 [ `first`、 `last`)。

最後の 2 つのメンバー関数の動作は同じことを除いて、最初の 2 つ`value`挿入された値を構築するために使用します。

##  <a name="key_eq"></a> key_eq

格納された等価比較関数のオブジェクトを返します。

```
key_equal key_eq() const;
```

### <a name="return-value"></a>戻り値

格納された等価比較関数のオブジェクト。

##  <a name="load_factor"></a> load_factor

計算し、コンテナーの現在のテーブル占有率を返します。 占有率は、バケットの数で割った値コンテナー内の要素の数です。

```
float load_factor() const;
```

### <a name="return-value"></a>戻り値

コンテナーのテーブル占有率。

##  <a name="max_load_factor"></a> max_load_factor

取得またはコンテナーの最大テーブル占有率を設定します。 最大テーブル占有率は要素の最大数、コンテナーの内部テーブルを拡張する前に、バケットにすることができます。

```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```

### <a name="parameters"></a>パラメーター

`_Newmax`

### <a name="return-value"></a>戻り値

1 つ目のメンバー関数は、格納されている最大テーブル占有率を返します。 2 番目のメンバー関数は、値は返されませんがスローされます、 [out_of_range](../../../standard-library/out-of-range-class.md)指定したテーブル占有率が有効でない場合は例外.

##  <a name="max_size"></a> max_size

アロケーターによって決定される、同時実行コンテナーの最大サイズを返します。 このメソッドはコンカレンシー セーフです。

```
size_type max_size() const;
```

### <a name="return-value"></a>戻り値

この同時実行コンテナーに挿入できる要素の最大数。

### <a name="remarks"></a>Remarks

この上限値実際にどのようなコンテナー実際に保持できるよりも高い場合があります。

##  <a name="operator_eq"></a> 演算子 =

別の `concurrent_unordered_set` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドはコンカレンシー セーフではありません。

```
concurrent_unordered_set& operator= (const concurrent_unordered_set& _Uset);

concurrent_unordered_set& operator= (concurrent_unordered_set&& _Uset);
```

### <a name="parameters"></a>パラメーター

*_Uset*<br/>
ソース `concurrent_unordered_set` オブジェクト。

### <a name="return-value"></a>戻り値

この `concurrent_unordered_set` オブジェクトへの参照。

### <a name="remarks"></a>Remarks

同時実行順序なしのセット内の既存の要素を消去した後`operator=`の内容を移動またはコピー`_Uset`セットを順序付けされておらず、同時にします。

##  <a name="rehash"></a> 流用しています

ハッシュ テーブルをリビルドします。

```
void rehash(size_type _Buckets);
```

### <a name="parameters"></a>パラメーター

*_Buckets*<br/>
必要なバケット数。

### <a name="remarks"></a>Remarks

メンバー関数は、バケット数を `_Buckets` 以上に変更し、必要に応じて、ハッシュ テーブルをリビルドします。 バケット数は 2 の累乗である必要があります。 場合いない 2 の累乗で、2 の累乗に切り上げられますされます。

スローされます、 [out_of_range](../../../standard-library/out-of-range-class.md)例外のバケットの数が有効でない場合 (0 またはバケットの最大数より大きい)。

##  <a name="size"></a> サイズ

この同時実行コンテナーの要素の数を返します。 このメソッドはコンカレンシー セーフです。

```
size_type size() const;
```

### <a name="return-value"></a>戻り値

コンテナー内の項目の数。

### <a name="remarks"></a>Remarks

同時実行の挿入がある場合は、同時実行コンテナー内の要素の数は、戻り値は読み取り専用でも前に、この関数の呼び出し直後後変更できます。

##  <a name="swap"></a> スワップ

2 つの `concurrent_unordered_set` オブジェクトのコンテンツを交換します。 このメソッドはコンカレンシー セーフではありません。

```
void swap(concurrent_unordered_set& _Uset);
```

### <a name="parameters"></a>パラメーター

*_Uset*<br/>
`concurrent_unordered_set`交換するオブジェクト。

##  <a name="unsafe_begin"></a> unsafe_begin

特定のバケットのこのコンテナーの最初の要素に反復子を返します。

```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
バケットのインデックス。

### <a name="return-value"></a>戻り値

バケットの先頭を指す反復子。

##  <a name="unsafe_bucket"></a> unsafe_bucket

このコンテナー内に特定のキーがマップされるバケットのインデックスを返します。

```
size_type unsafe_bucket(const key_type& KVal) const;
```

### <a name="parameters"></a>パラメーター

*KVal*<br/>
検索対象の要素のキー。

### <a name="return-value"></a>戻り値

このコンテナー内のキーのバケットのインデックス。

##  <a name="unsafe_bucket_count"></a> unsafe_bucket_count

このコンテナー内の現在のバケット数を返します。

```
size_type unsafe_bucket_count() const;
```

### <a name="return-value"></a>戻り値

このコンテナー内のバケットの現在数。

##  <a name="unsafe_bucket_size"></a> unsafe_bucket_size

このコンテナーの特定のバケット内の項目の数を返します。

```
size_type unsafe_bucket_size(size_type _Bucket);
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
検索するバケット。

### <a name="return-value"></a>戻り値

このコンテナー内のバケットの現在数。

##  <a name="unsafe_cbegin"></a> unsafe_cbegin

特定のバケットのこのコンテナーの最初の要素に反復子を返します。

```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
バケットのインデックス。

### <a name="return-value"></a>戻り値

バケットの先頭を指す反復子。

##  <a name="unsafe_cend"></a> unsafe_cend

位置を特定のバケット内の最後の要素を指す反復子を返します。

```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
バケットのインデックス。

### <a name="return-value"></a>戻り値

バケットの先頭を指す反復子。

##  <a name="unsafe_end"></a> unsafe_end

特定のバケットのこのコンテナーの最後の要素に反復子を返します。

```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```

### <a name="parameters"></a>パラメーター

*_Bucket*<br/>
バケットのインデックス。

### <a name="return-value"></a>戻り値

バケットの末尾を指す反復子。

##  <a name="unsafe_erase"></a> unsafe_erase

`concurrent_unordered_set` から指定した位置にある要素を削除します。 このメソッドはコンカレンシー セーフではありません。

```
iterator unsafe_erase(
    const_iterator _Where);

size_type unsafe_erase(
    const key_type& KVal);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);
```

### <a name="parameters"></a>パラメーター

*_Where*<br/>
消去する反復子の位置。

*KVal*<br/>
消去するキー値。

*first*<br/>
*last*<br/>
反復子。

### <a name="return-value"></a>戻り値

最初の 2 つのメンバー関数は、削除された要素の後に残る最初の要素を指定する反復子を返しますまたは[エンド](#end)() そのような要素が存在しない場合。 3 つ目のメンバー関数は削除する要素の数を返します。

### <a name="remarks"></a>Remarks

1 つ目のメンバー関数は、`_Where` が指す要素を削除します。 2 番目のメンバー関数は、範囲内の要素を削除する [ `_Begin`、 `_End`)。

3 番目のメンバー関数は、区切られた範囲内の要素を削除する[equal_range](#equal_range)(KVal)。

##  <a name="unsafe_max_bucket_count"></a> unsafe_max_bucket_count

このコンテナー内のバケットの最大数を返します。

```
size_type unsafe_max_bucket_count() const;
```

### <a name="return-value"></a>戻り値

このコンテナー内のバケットの最大数。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)
