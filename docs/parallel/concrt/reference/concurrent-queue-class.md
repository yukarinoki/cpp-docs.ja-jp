---
title: concurrent_queue クラス
ms.date: 11/04/2016
f1_keywords:
- concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::concurrent_queue
- CONCURRENT_QUEUE/concurrency::concurrent_queue::clear
- CONCURRENT_QUEUE/concurrency::concurrent_queue::empty
- CONCURRENT_QUEUE/concurrency::concurrent_queue::get_allocator
- CONCURRENT_QUEUE/concurrency::concurrent_queue::push
- CONCURRENT_QUEUE/concurrency::concurrent_queue::try_pop
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_begin
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_end
- CONCURRENT_QUEUE/concurrency::concurrent_queue::unsafe_size
helpviewer_keywords:
- concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
ms.openlocfilehash: a117a040adbf7f3aa316c346489bd2731d6c2402
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230351"
---
# <a name="concurrent_queue-class"></a>concurrent_queue クラス

`concurrent_queue` クラスは、キューの要素に先入れ先出し方式でアクセスできるようにするシーケンス コンテナー クラスです。 これを使用すると、`push`、`try_pop` などの特定のコンカレンシー セーフな操作を実行できます。 ここでは、同時実行セーフとは、ポインターまたは反復子が常に有効であることを意味します。 これは、要素の初期化、または特定のトラバーサルの順序の保証ではありません。

## <a name="syntax"></a>構文

```cpp
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
キューに格納される要素のデータ型。

*_Ax*<br/>
この同時実行キューのメモリの割り当てと解放に関する詳細をカプセル化する、格納されているアロケーターオブジェクトを表す型。 この引数は省略可能であり、既定値は `allocator<T>` です。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`allocator_type`|同時実行キューのアロケータークラスを表す型。|
|`const_iterator`|**`const`** 同時実行キュー内の要素に対するスレッドセーフではない反復子を表す型。|
|`const_reference`|**`const`** 読み取りと操作の実行のために、同時実行キューに格納されている要素への参照を提供する型 **`const`** 。|
|`difference_type`|同時実行キュー内の2つの要素間の符号付き距離を提供する型。|
|`iterator`|同時実行キュー内の要素に対するスレッドセーフではない反復子を表す型。|
|`reference`|同時実行キューに格納されている要素への参照を提供する型。|
|`size_type`|同時実行キュー内の要素の数をカウントする型。|
|`value_type`|同時実行キューに格納されているデータ型を表す型。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[concurrent_queue](#ctor)|オーバーロードされます。 同時実行キューを構築します。|
|[~ concurrent_queue デストラクター](#dtor)|同時実行キューを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[オフ](#clear)|同時実行キューをクリアし、現在エンキューされている要素を破棄します。 このメソッドはコンカレンシー セーフではありません。|
|[empty](#empty)|このメソッドが呼び出された時点で同時実行キューが空かどうかをテストします。 このメソッドはコンカレンシー セーフです。|
|[get_allocator](#get_allocator)|同時実行キューの構築に使用されるアロケーターのコピーを返します。 このメソッドはコンカレンシー セーフです。|
|[push](#push)|オーバーロードされます。 同時実行キューの末尾に項目をエンキューします。 このメソッドはコンカレンシー セーフです。|
|[try_pop](#try_pop)|デキューが使用可能な場合は、キューから項目を取得します。 このメソッドはコンカレンシー セーフです。|
|[unsafe_begin](#unsafe_begin)|オーバーロードされます。 `iterator`同時実行キューの先頭に、型または型の反復子 `const_iterator` を返します。 このメソッドはコンカレンシー セーフではありません。|
|[unsafe_end](#unsafe_end)|オーバーロードされます。 `iterator`同時実行キューの末尾に、型または型の反復子 `const_iterator` を返します。 このメソッドはコンカレンシー セーフではありません。|
|[unsafe_size](#unsafe_size)|キュー内の項目の数を返します。 このメソッドはコンカレンシー セーフではありません。|

## <a name="remarks"></a>解説

詳細については、「[並列コンテナーとオブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`concurrent_queue`

## <a name="requirements"></a>必要条件

**ヘッダー:** concurrent_queue

**名前空間:** concurrency

## <a name="clear"></a><a name="clear"></a>クリア

同時実行キューをクリアし、現在エンキューされている要素を破棄します。 このメソッドはコンカレンシー セーフではありません。

```cpp
void clear();
```

## <a name="concurrent_queue"></a><a name="ctor"></a>concurrent_queue

同時実行キューを構築します。

```cpp
explicit concurrent_queue(
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    const concurrent_queue& _OtherQ,
    const allocator_type& _Al = allocator_type());

concurrent_queue(
    concurrent_queue&& _OtherQ,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_queue(_InputIterator _Begin,
    _InputIterator _End);
```

### <a name="parameters"></a>パラメーター

*_InputIterator*<br/>
値の範囲を指定する入力反復子の型。

*_Al*<br/>
このオブジェクトに対して使用するアロケーター クラス。

*_OtherQ*<br/>
要素のコピー元または移動元の `concurrent_queue` オブジェクト。

*_Begin*<br/>
コピーする要素範囲内の最初の要素の位置。

*_End*<br/>
コピーする要素範囲を超える最初の要素の位置。

### <a name="remarks"></a>解説

すべてのコンストラクターは、アロケーターオブジェクト `_Al` を格納し、キューを初期化します。

最初のコンストラクターは、空の初期キューを指定し、使用するアロケーターの型を明示的に指定します。

2番目のコンストラクターは、同時実行キューのコピーを指定し `_OtherQ` ます。

3番目のコンストラクターは、同時実行キューの移動を指定し `_OtherQ` ます。

4番目のコンストラクターは、反復子の範囲 [,) によって指定された値を指定し `_Begin` `_End` ます。

## <a name="concurrent_queue"></a><a name="dtor"></a>~ concurrent_queue

同時実行キューを破棄します。

```cpp
~concurrent_queue();
```

## <a name="empty"></a><a name="empty"></a>指定

このメソッドが呼び出された時点で同時実行キューが空かどうかをテストします。 このメソッドはコンカレンシー セーフです。

```cpp
bool empty() const;
```

### <a name="return-value"></a>戻り値

**`true`** 先ほど見た時点で、同時実行キューが空だった場合は **`false`** 。それ以外の場合は。

### <a name="remarks"></a>解説

このメソッドは、メソッド、、およびメソッドの呼び出しに関して同時実行セーフであるのに対し `push` `try_pop` `empty` 、呼び出し元スレッドによって検査されたときに返される値が正しくない可能性があります。

## <a name="get_allocator"></a><a name="get_allocator"></a>get_allocator

同時実行キューの構築に使用されるアロケーターのコピーを返します。 このメソッドはコンカレンシー セーフです。

```cpp
allocator_type get_allocator() const;
```

### <a name="return-value"></a>戻り値

同時実行キューを構築するために使用されるアロケーターのコピー。

## <a name="push"></a><a name="push"></a>押し付け

同時実行キューの末尾に項目をエンキューします。 このメソッドはコンカレンシー セーフです。

```cpp
void push(const T& _Src);

void push(T&& _Src);
```

### <a name="parameters"></a>パラメーター

*_Src*<br/>
キューに追加する項目。

### <a name="remarks"></a>解説

`push`は、メソッド、、およびの呼び出しに関して、同時実行セーフです `push` `try_pop` `empty` 。

## <a name="try_pop"></a><a name="try_pop"></a>try_pop

デキューが使用可能な場合は、キューから項目を取得します。 このメソッドはコンカレンシー セーフです。

```cpp
bool try_pop(T& _Dest);
```

### <a name="parameters"></a>パラメーター

*_Dest*<br/>
デキューされた項目を格納する場所への参照。

### <a name="return-value"></a>戻り値

**`true`** 項目が正常にデキューされた場合は **`false`** 。それ以外の場合は。

### <a name="remarks"></a>解説

項目が正常にデキューされた場合、パラメーターは `_Dest` デキューされた値を受け取り、キューに保持されていた元の値は破棄され、この関数はを返し **`true`** ます。 デキューする項目がない場合、この関数はブロックせずにを返し、 **`false`** パラメーターの内容 `_Dest` は未定義になります。

`try_pop`は、メソッド、、およびの呼び出しに関して、同時実行セーフです `push` `try_pop` `empty` 。

## <a name="unsafe_begin"></a><a name="unsafe_begin"></a>unsafe_begin

`iterator`同時実行キューの先頭に、型または型の反復子 `const_iterator` を返します。 このメソッドはコンカレンシー セーフではありません。

```cpp
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```

### <a name="return-value"></a>戻り値

`iterator` `const_iterator` 同時実行キューオブジェクトの先頭に対する、または型の反復子。

### <a name="remarks"></a>解説

クラスの反復子は、主にデバッグを目的としていますが、 `concurrent_queue` これらは低速であり、イテレーションは他のキュー操作に対して同時実行セーフではありません。

## <a name="unsafe_end"></a><a name="unsafe_end"></a>unsafe_end

`iterator`同時実行キューの末尾に、型または型の反復子 `const_iterator` を返します。 このメソッドはコンカレンシー セーフではありません。

```cpp
iterator unsafe_end();

const_iterator unsafe_end() const;
```

### <a name="return-value"></a>戻り値

`iterator` `const_iterator` 同時実行キューの末尾に対する、型または型の反復子。

### <a name="remarks"></a>解説

クラスの反復子は、主にデバッグを目的としていますが、 `concurrent_queue` これらは低速であり、イテレーションは他のキュー操作に対して同時実行セーフではありません。

## <a name="unsafe_size"></a><a name="unsafe_size"></a>unsafe_size

キュー内の項目の数を返します。 このメソッドはコンカレンシー セーフではありません。

```cpp
size_type unsafe_size() const;
```

### <a name="return-value"></a>戻り値

同時実行キューのサイズ。

### <a name="remarks"></a>解説

`unsafe_size`は同時実行セーフではなく、メソッド、、およびの呼び出しで同時に呼び出された場合、正しくない結果が生成される可能性があり `push` `try_pop` `empty` ます。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
