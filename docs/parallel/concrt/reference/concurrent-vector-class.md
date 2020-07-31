---
title: concurrent_vector クラス
ms.date: 11/04/2016
f1_keywords:
- concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::concurrent_vector
- CONCURRENT_VECTOR/concurrency::concurrent_vector::assign
- CONCURRENT_VECTOR/concurrency::concurrent_vector::at
- CONCURRENT_VECTOR/concurrency::concurrent_vector::back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::begin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::capacity
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::cend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::clear
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::crend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::empty
- CONCURRENT_VECTOR/concurrency::concurrent_vector::end
- CONCURRENT_VECTOR/concurrency::concurrent_vector::front
- CONCURRENT_VECTOR/concurrency::concurrent_vector::get_allocator
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_by
- CONCURRENT_VECTOR/concurrency::concurrent_vector::grow_to_at_least
- CONCURRENT_VECTOR/concurrency::concurrent_vector::max_size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::push_back
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rbegin
- CONCURRENT_VECTOR/concurrency::concurrent_vector::rend
- CONCURRENT_VECTOR/concurrency::concurrent_vector::reserve
- CONCURRENT_VECTOR/concurrency::concurrent_vector::resize
- CONCURRENT_VECTOR/concurrency::concurrent_vector::shrink_to_fit
- CONCURRENT_VECTOR/concurrency::concurrent_vector::size
- CONCURRENT_VECTOR/concurrency::concurrent_vector::swap
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
ms.openlocfilehash: 9144fd0870bfb72e923a7271ffdd655e03a9bd57
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215843"
---
# <a name="concurrent_vector-class"></a>concurrent_vector クラス

`concurrent_vector` クラスは、任意の要素にランダムにアクセスできるようにするシーケンス コンテナー クラスです。 これを使用すると、コンカレンシー セーフな追加、要素アクセス、反復子アクセス、および反復子走査の各操作を実行できます。 ここでは、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化、または特定のトラバーサルの順序の保証ではありません。

## <a name="syntax"></a>構文

```cpp
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
private details::_Concurrent_vector_base_v4;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
ベクターに格納される要素のデータ型。

*_Ax*<br/>
同時実行ベクターのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `allocator<T>` です。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`allocator_type`|同時実行ベクターのアロケータークラスを表す型。|
|`const_iterator`|**`const`** 同時実行ベクター内の要素を読み取ることができるランダムアクセス反復子を提供する型。|
|`const_pointer`|**`const`** 同時実行ベクター内の要素へのポインターを提供する型。|
|`const_reference`|**`const`** 読み取りと操作の実行のために、同時実行ベクターに格納されている要素への参照を提供する型 **`const`** 。|
|`const_reverse_iterator`|同時実行ベクター内の任意の要素を読み取ることができるランダムアクセス反復子を提供する型 **`const`** 。|
|`difference_type`|同時実行ベクター内の2つの要素間の符号付き距離を提供する型。|
|`iterator`|同時実行ベクター内の任意の要素を読み取ることができるランダムアクセス反復子を提供する型。 反復子を使用した要素の変更は、同時実行セーフではありません。|
|`pointer`|同時実行ベクター内の要素へのポインターを提供する型。|
|`reference`|同時実行ベクターに格納されている要素への参照を提供する型。|
|`reverse_iterator`|反転された同時実行ベクター内の任意の要素を読み取ることができるランダムアクセス反復子を提供する型。 反復子を使用した要素の変更は、同時実行セーフではありません。|
|`size_type`|同時実行ベクター内の要素の数をカウントする型。|
|`value_type`|同時実行ベクターに格納されているデータ型を表す型。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[concurrent_vector](#ctor)|オーバーロードされます。 同時実行ベクターを構築します。|
|[~ concurrent_vector デストラクター](#dtor)|すべての要素を消去し、この同時実行ベクターを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[assign](#assign)|オーバーロードされます。 同時実行ベクターの要素を消去し、 `_N` のコピー `_Item` 、または反復子の範囲 [,) によって指定された値を代入し `_Begin` `_End` ます。 このメソッドはコンカレンシー セーフではありません。|
|[at](#at)|オーバーロードされます。 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは、読み取り操作に対して同時実行セーフであり、値 `_Index` が同時実行ベクターのサイズよりも小さいことを確認した場合に限り、ベクターを拡大しています。|
|[戻る](#back)|オーバーロードされます。 **`const`** 同時実行ベクター内の最後の要素への参照または参照を返します。 同時実行ベクターが空の場合、戻り値は未定義になります。 このメソッドはコンカレンシー セーフです。|
|[初め](#begin)|オーバーロードされます。 `iterator`同時実行ベクターの先頭に、型または型の反復子 `const_iterator` を返します。 このメソッドはコンカレンシー セーフです。|
|[capacity](#capacity)|より多くのメモリを割り当てることなく、同時実行ベクターを拡張できる最大サイズを返します。 このメソッドはコンカレンシー セーフです。|
|[cbegin](#cbegin)|`const_iterator`同時実行ベクターの先頭に型の反復子を返します。 このメソッドはコンカレンシー セーフです。|
|[cend](#cend)|`const_iterator`同時実行ベクターの末尾に型の反復子を返します。 このメソッドはコンカレンシー セーフです。|
|[オフ](#clear)|同時実行ベクター内のすべての要素を消去します。 このメソッドはコンカレンシー セーフではありません。|
|[crbegin](#crbegin)|`const_reverse_iterator`同時実行ベクターの先頭に型の反復子を返します。 このメソッドはコンカレンシー セーフです。|
|[crend](#crend)|`const_reverse_iterator`同時実行ベクターの末尾に型の反復子を返します。 このメソッドはコンカレンシー セーフです。|
|[empty](#empty)|このメソッドが呼び出されたときに、同時実行ベクターが空かどうかをテストします。 このメソッドはコンカレンシー セーフです。|
|[end](#end)|オーバーロードされます。 `iterator`同時実行ベクターの末尾に、型または型の反復子 `const_iterator` を返します。 このメソッドはコンカレンシー セーフです。|
|[外側](#front)|オーバーロードされます。 **`const`** 同時実行ベクター内の最初の要素への参照または参照を返します。 同時実行ベクターが空の場合、戻り値は未定義になります。 このメソッドはコンカレンシー セーフです。|
|[get_allocator](#get_allocator)|同時実行ベクターの構築に使用されるアロケーターのコピーを返します。 このメソッドはコンカレンシー セーフです。|
|[grow_by](#grow_by)|オーバーロードされます。 この同時実行ベクターを `_Delta` 要素で拡大します。 このメソッドはコンカレンシー セーフです。|
|[grow_to_at_least](#grow_to_at_least)|は、少なくとも要素が含まれるまで、この同時実行ベクター `_N` を拡大します。 このメソッドはコンカレンシー セーフです。|
|[max_size](#max_size)|同時実行ベクターが保持できる要素の最大数を返します。 このメソッドはコンカレンシー セーフです。|
|[push_back](#push_back)|オーバーロードされます。 指定された項目を同時実行ベクターの末尾に追加します。 このメソッドはコンカレンシー セーフです。|
|[rbegin](#rbegin)|オーバーロードされます。 `reverse_iterator`同時実行ベクターの先頭に、型または型の反復子 `const_reverse_iterator` を返します。 このメソッドはコンカレンシー セーフです。|
|[rend](#rend)|オーバーロードされます。 `reverse_iterator`同時実行ベクターの末尾に、型または型の反復子 `const_reverse_iterator` を返します。 このメソッドはコンカレンシー セーフです。|
|[省](#reserve)|後でより多くのメモリを割り当てずに、同時実行ベクターのサイズを大きくするのに十分な領域を割り当て `_N` ます。 このメソッドはコンカレンシー セーフではありません。|
|[サイズ](#resize)|オーバーロードされます。 必要に応じて、同時実行ベクターのサイズを要求されたサイズに変更し、要素を削除または追加します。 このメソッドはコンカレンシー セーフではありません。|
|[shrink_to_fit](#shrink_to_fit)|断片化を軽減し、メモリ使用量を最適化するために、同時実行ベクターの内部表現を圧縮します。 このメソッドはコンカレンシー セーフではありません。|
|[size](#size)|同時実行ベクター内の要素の数を返します。 このメソッドはコンカレンシー セーフです。|
|[スワップ](#swap)|2つの同時実行ベクターの内容を交換します。 このメソッドはコンカレンシー セーフではありません。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator\[\]](#operator_at)|オーバーロードされます。 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは、読み取り操作に対して同時実行セーフであり、値 `_Index` が同時実行ベクターのサイズよりも小さいことを確認した場合に限り、ベクターを拡大しています。|
|[operator =](#operator_eq)|オーバーロードされます。 別の `concurrent_vector` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドはコンカレンシー セーフではありません。|

## <a name="remarks"></a>解説

クラスの詳細につい `concurrent_vector` ては、「[並列コンテナーとオブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`_Concurrent_vector_base_v4`

`_Allocator_base`

`concurrent_vector`

## <a name="requirements"></a>必要条件

**ヘッダー:** concurrent_vector

**名前空間:** concurrency

## <a name="assign"></a><a name="assign"></a>割り当てる

同時実行ベクターの要素を消去し、 `_N` のコピー `_Item` 、または反復子の範囲 [,) によって指定された値を代入し `_Begin` `_End` ます。 このメソッドはコンカレンシー セーフではありません。

```cpp
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```

### <a name="parameters"></a>パラメーター

*_InputIterator*<br/>
指定した反復子の型。

*_N*<br/>
同時実行ベクターにコピーする項目の数。

*_Item*<br/>
同時実行ベクターを埋めるために使用される値への参照。

*_Begin*<br/>
ソース範囲の最初の要素を指す反復子。

*_End*<br/>
ソース範囲の最後の要素の1つ後ろの反復子。

### <a name="remarks"></a>解説

`assign`は同時実行セーフではありません。 このメソッドを呼び出すときに、他のスレッドが同時実行ベクターに対してメソッドを呼び出していないことを確認する必要があります。

## <a name="at"></a><a name="at"></a>(

同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは、読み取り操作に対して同時実行セーフであり、値 `_Index` が同時実行ベクターのサイズよりも小さいことを確認した場合に限り、ベクターを拡大しています。

```cpp
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```

### <a name="parameters"></a>パラメーター

*_Index*<br/>
取得する要素のインデックス。

### <a name="return-value"></a>戻り値

指定したインデックス位置にある項目への参照。

### <a name="remarks"></a>解説

非参照を返す関数のバージョンを使用して、 `at` **`const`** 異なるスレッドから要素に同時に書き込むことはできません。 同じデータ要素に対する同時読み取り操作と書き込み操作を同期するには、別の同期オブジェクトを使用する必要があります。

が同時実行ベクターのサイズ以上である場合、または `out_of_range` `_Index` `range_error` インデックスがベクターの分割された部分のインデックスの場合、メソッドはをスローします。 ベクターの破損の詳細については、「[並列コンテナーとオブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。

## <a name="back"></a><a name="back"></a>戻る

**`const`** 同時実行ベクター内の最後の要素への参照または参照を返します。 同時実行ベクターが空の場合、戻り値は未定義になります。 このメソッドはコンカレンシー セーフです。

```cpp
reference back();

const_reference back() const;
```

### <a name="return-value"></a>戻り値

**`const`** 同時実行ベクター内の最後の要素への参照または参照。

## <a name="begin"></a><a name="begin"></a>初め

`iterator`同時実行ベクターの先頭に、型または型の反復子 `const_iterator` を返します。 このメソッドはコンカレンシー セーフです。

```cpp
iterator begin();

const_iterator begin() const;
```

### <a name="return-value"></a>戻り値

`iterator` `const_iterator` 同時実行ベクターの先頭に対する、型または型の反復子。

## <a name="capacity"></a><a name="capacity"></a>capacity

より多くのメモリを割り当てることなく、同時実行ベクターを拡張できる最大サイズを返します。 このメソッドはコンカレンシー セーフです。

```cpp
size_type capacity() const;
```

### <a name="return-value"></a>戻り値

より多くのメモリを割り当てることなく、同時実行ベクターを拡張できる最大サイズ。

### <a name="remarks"></a>解説

C++ 標準ライブラリとは異なり `vector` 、 `concurrent_vector` オブジェクトがより多くのメモリを割り当てると、既存の要素は移動されません。

## <a name="cbegin"></a><a name="cbegin"></a>cbegin

`const_iterator`同時実行ベクターの先頭に型の反復子を返します。 このメソッドはコンカレンシー セーフです。

```cpp
const_iterator cbegin() const;
```

### <a name="return-value"></a>戻り値

`const_iterator`同時実行ベクターの先頭に対する型の反復子。

## <a name="cend"></a><a name="cend"></a>cend

`const_iterator`同時実行ベクターの末尾に型の反復子を返します。 このメソッドはコンカレンシー セーフです。

```cpp
const_iterator cend() const;
```

### <a name="return-value"></a>戻り値

`const_iterator`同時実行ベクターの末尾への型の反復子。

## <a name="clear"></a><a name="clear"></a>クリア

同時実行ベクター内のすべての要素を消去します。 このメソッドはコンカレンシー セーフではありません。

```cpp
void clear();
```

### <a name="remarks"></a>解説

`clear`は同時実行セーフではありません。 このメソッドを呼び出すときに、他のスレッドが同時実行ベクターに対してメソッドを呼び出していないことを確認する必要があります。 `clear`内部配列は解放されません。 内部配列を解放するには、の後に関数を呼び出し `shrink_to_fit` `clear` ます。

## <a name="concurrent_vector"></a><a name="ctor"></a>concurrent_vector

同時実行ベクターを構築します。

```cpp
explicit concurrent_vector(
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector(
    const concurrent_vector<T,
    M>& _Vector,
    const allocator_type& _Al = allocator_type());

concurrent_vector(
    concurrent_vector&& _Vector);

explicit concurrent_vector(
    size_type _N);

concurrent_vector(
    size_type _N,
    const_reference _Item,
    const allocator_type& _Al = allocator_type());

template<class _InputIterator>
concurrent_vector(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());
```

### <a name="parameters"></a>パラメーター

*M*<br/>
ソース ベクターのアロケーターの型。

*_InputIterator*<br/>
入力反復子の型。

*_Al*<br/>
このオブジェクトに対して使用するアロケーター クラス。

*_Vector*<br/>
要素のコピー元または移動元の `concurrent_vector` オブジェクト。

*_N*<br/>
`concurrent_vector` オブジェクトの初期容量。

*_Item*<br/>
構築されたオブジェクトの要素の値。

*_Begin*<br/>
コピーする要素範囲内の最初の要素の位置。

*_End*<br/>
コピーする要素範囲を超える最初の要素の位置。

### <a name="remarks"></a>解説

すべてのコンストラクターは、アロケーター オブジェクト `_Al` を格納し、ベクターを初期化します。

最初のコンストラクターは、空の初期ベクターを指定し、明示的にアロケーターの型を指定します。 使用されます。

2 つ目および 3 つ目のコンストラクターは、同時実行ベクター `_Vector` のコピーを指定します。

4 番目のコンストラクターは、同時実行ベクター `_Vector` の移動を指定します。

5番目のコンストラクターは、 `_N` クラスの既定値の要素の指定された数 () の繰り返しを指定し `T` ます。

6番目のコンストラクターは、値の () 要素の繰り返しを指定し `_N` `_Item` ます。

最後のコンストラクターは、反復子の範囲 [,) によって指定された値を指定し `_Begin` `_End` ます。

## <a name="concurrent_vector"></a><a name="dtor"></a>~ concurrent_vector

すべての要素を消去し、この同時実行ベクターを破棄します。

```cpp
~concurrent_vector();
```

## <a name="crbegin"></a><a name="crbegin"></a>crbegin

`const_reverse_iterator`同時実行ベクターの先頭に型の反復子を返します。 このメソッドはコンカレンシー セーフです。

```cpp
const_reverse_iterator crbegin() const;
```

### <a name="return-value"></a>戻り値

`const_reverse_iterator`同時実行ベクターの先頭に対する型の反復子。

## <a name="crend"></a><a name="crend"></a>crend

`const_reverse_iterator`同時実行ベクターの末尾に型の反復子を返します。 このメソッドはコンカレンシー セーフです。

```cpp
const_reverse_iterator crend() const;
```

### <a name="return-value"></a>戻り値

`const_reverse_iterator`同時実行ベクターの末尾への型の反復子。

## <a name="empty"></a><a name="empty"></a>指定

このメソッドが呼び出されたときに、同時実行ベクターが空かどうかをテストします。 このメソッドはコンカレンシー セーフです。

```cpp
bool empty() const;
```

### <a name="return-value"></a>戻り値

**`true`** 関数が呼び出された時点でベクターが空だった場合は **`false`** 。それ以外の場合は。

## <a name="end"></a><a name="end"></a>終わり

`iterator`同時実行ベクターの末尾に、型または型の反復子 `const_iterator` を返します。 このメソッドはコンカレンシー セーフです。

```cpp
iterator end();

const_iterator end() const;
```

### <a name="return-value"></a>戻り値

`iterator` `const_iterator` 同時実行ベクターの末尾に対する、または型の反復子。

## <a name="front"></a><a name="front"></a>外側

**`const`** 同時実行ベクター内の最初の要素への参照または参照を返します。 同時実行ベクターが空の場合、戻り値は未定義になります。 このメソッドはコンカレンシー セーフです。

```cpp
reference front();

const_reference front() const;
```

### <a name="return-value"></a>戻り値

**`const`** 同時実行ベクター内の最初の要素への参照または参照。

## <a name="get_allocator"></a><a name="get_allocator"></a>get_allocator

同時実行ベクターの構築に使用されるアロケーターのコピーを返します。 このメソッドはコンカレンシー セーフです。

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>戻り値

オブジェクトの構築に使用されるアロケーターのコピー `concurrent_vector` 。

## <a name="grow_by"></a><a name="grow_by"></a>grow_by

この同時実行ベクターを `_Delta` 要素で拡大します。 このメソッドはコンカレンシー セーフです。

```cpp
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```

### <a name="parameters"></a>パラメーター

*_Delta*<br/>
オブジェクトに追加する要素の数。

*_Item*<br/>
新しい要素の初期化に使用する値。

### <a name="return-value"></a>戻り値

最初の項目に追加される反復子。

### <a name="remarks"></a>解説

`_Item`が指定されていない場合は、新しい要素が既定で構築されます。

## <a name="grow_to_at_least"></a><a name="grow_to_at_least"></a>grow_to_at_least

は、少なくとも要素が含まれるまで、この同時実行ベクター `_N` を拡大します。 このメソッドはコンカレンシー セーフです。

```cpp
iterator grow_to_at_least(size_type _N);
```

### <a name="parameters"></a>パラメーター

*_N*<br/>
オブジェクトの新しい最小サイズ `concurrent_vector` 。

### <a name="return-value"></a>戻り値

追加されたシーケンスの先頭を指す反復子 `_N` 。要素が追加されなかった場合は、インデックスの位置にある要素。

## <a name="max_size"></a><a name="max_size"></a>max_size

同時実行ベクターが保持できる要素の最大数を返します。 このメソッドはコンカレンシー セーフです。

```cpp
size_type max_size() const;
```

### <a name="return-value"></a>戻り値

オブジェクトが保持できる要素の最大数 `concurrent_vector` 。

## <a name="operator"></a><a name="operator_eq"></a>operator =

別の `concurrent_vector` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドはコンカレンシー セーフではありません。

```cpp
concurrent_vector& operator= (
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector& operator= (
    const concurrent_vector<T, M>& _Vector);

concurrent_vector& operator= (
    concurrent_vector&& _Vector);
```

### <a name="parameters"></a>パラメーター

*M*<br/>
ソース ベクターのアロケーターの型。

*_Vector*<br/>
ソース `concurrent_vector` オブジェクト。

### <a name="return-value"></a>戻り値

この `concurrent_vector` オブジェクトへの参照。

## <a name="operator"></a><a name="operator_at"></a>演算子 []

同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは、読み取り操作に対して同時実行セーフであり、値 `_Index` が同時実行ベクターのサイズよりも小さいことを確認した場合に限り、ベクターを拡大しています。

```cpp
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```

### <a name="parameters"></a>パラメーター

*_Index*<br/>
取得する要素のインデックス。

### <a name="return-value"></a>戻り値

指定したインデックス位置にある項目への参照。

### <a name="remarks"></a>解説

非参照を返すのバージョンを使用して、 `operator []` **`const`** 異なるスレッドから要素に同時に書き込むことはできません。 同じデータ要素に対する同時読み取り操作と書き込み操作を同期するには、別の同期オブジェクトを使用する必要があります。

`_Index`が同時実行ベクターへの有効なインデックスであることを確認するために、境界チェックは実行されません。

## <a name="push_back"></a><a name="push_back"></a>push_back

指定された項目を同時実行ベクターの末尾に追加します。 このメソッドはコンカレンシー セーフです。

```cpp
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```

### <a name="parameters"></a>パラメーター

*_Item*<br/>
追加する値。

### <a name="return-value"></a>戻り値

項目を追加する反復子。

## <a name="rbegin"></a><a name="rbegin"></a>rbegin

`reverse_iterator`同時実行ベクターの先頭に、型または型の反復子 `const_reverse_iterator` を返します。 このメソッドはコンカレンシー セーフです。

```cpp
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```

### <a name="return-value"></a>戻り値

`reverse_iterator` `const_reverse_iterator` 同時実行ベクターの先頭に対する、型または型の反復子。

## <a name="rend"></a><a name="rend"></a>rend

`reverse_iterator`同時実行ベクターの末尾に、型または型の反復子 `const_reverse_iterator` を返します。 このメソッドはコンカレンシー セーフです。

```cpp
reverse_iterator rend();

const_reverse_iterator rend() const;
```

### <a name="return-value"></a>戻り値

`reverse_iterator` `const_reverse_iterator` 同時実行ベクターの末尾に対する、または型の反復子。

## <a name="reserve"></a><a name="reserve"></a>省

後でより多くのメモリを割り当てずに、同時実行ベクターのサイズを大きくするのに十分な領域を割り当て `_N` ます。 このメソッドはコンカレンシー セーフではありません。

```cpp
void reserve(size_type _N);
```

### <a name="parameters"></a>パラメーター

*_N*<br/>
領域を予約する要素の数。

### <a name="remarks"></a>解説

`reserve`は同時実行セーフではありません。 このメソッドを呼び出すときに、他のスレッドが同時実行ベクターに対してメソッドを呼び出していないことを確認する必要があります。 メソッドから制御が戻った後の同時実行ベクターの容量は、要求された予約よりも大きくなる可能性があります。

## <a name="resize"></a><a name="resize"></a>サイズ

必要に応じて、同時実行ベクターのサイズを要求されたサイズに変更し、要素を削除または追加します。 このメソッドはコンカレンシー セーフではありません。

```cpp
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```

### <a name="parameters"></a>パラメーター

*_N*<br/>
Concurrent_vector の新しいサイズ。

*val*<br/>
新しいサイズが元のサイズより大きい場合に、ベクターに追加される新しい要素の値。 値を省略した場合、新しいオブジェクトにはその型の既定値が割り当てられます。

### <a name="remarks"></a>解説

コンテナーのサイズが要求されたサイズより小さい場合は、要求されたサイズに達するまで要素がベクターに追加されます。 コンテナーのサイズが要求されたサイズよりも大きい場合、コンテナーのサイズに達するまで、コンテナーの末尾に近い要素が削除され `_N` ます。 コンテナーの現在のサイズが要求されたサイズと同じ場合は、何も実行されません。

`resize`は、同時実行セーフではありません。 このメソッドを呼び出すときに、他のスレッドが同時実行ベクターに対してメソッドを呼び出していないことを確認する必要があります。

## <a name="shrink_to_fit"></a><a name="shrink_to_fit"></a>shrink_to_fit

断片化を軽減し、メモリ使用量を最適化するために、同時実行ベクターの内部表現を圧縮します。 このメソッドはコンカレンシー セーフではありません。

```cpp
void shrink_to_fit();
```

### <a name="remarks"></a>解説

このメソッドは、メモリの移動の要素を内部的に再割り当てし、すべての反復子を無効にします。 `shrink_to_fit`は同時実行セーフではありません。 この関数を呼び出すときに、他のスレッドが同時実行ベクターに対してメソッドを呼び出していないことを確認する必要があります。

## <a name="size"></a><a name="size"></a>幅

同時実行ベクター内の要素の数を返します。 このメソッドはコンカレンシー セーフです。

```cpp
size_type size() const;
```

### <a name="return-value"></a>戻り値

このオブジェクト内の要素の数 `concurrent_vector` 。

### <a name="remarks"></a>解説

返されるサイズには、関数の呼び出しによって追加されたすべての要素 `push_back` 、またはこのメソッドを呼び出す前に完了した拡張操作が含まれることが保証されます。 ただし、いずれかの拡張メソッドの同時呼び出しによって割り当てられているが、まだ構築中の要素が含まれる場合もあります。

## <a name="swap"></a><a name="swap"></a>フォト

2つの同時実行ベクターの内容を交換します。 このメソッドはコンカレンシー セーフではありません。

```cpp
void swap(concurrent_vector& _Vector);
```

### <a name="parameters"></a>パラメーター

*_Vector*<br/>
コンテンツの交換先の `concurrent_vector` オブジェクト。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)
