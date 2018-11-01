---
title: concurrent_priority_queue クラス
ms.date: 11/04/2016
f1_keywords:
- concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::concurrent_priority_queue
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::clear
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::empty
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::get_allocator
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::push
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::size
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::swap
- CONCURRENT_PRIORITY_QUEUE/concurrency::concurrent_priority_queue::try_pop
helpviewer_keywords:
- concurrent_priority_queue class
ms.assetid: 3e740381-0f4e-41fc-8b66-ad0bb55f17a3
ms.openlocfilehash: a75d413874056d57f0d474f44e514cf93f273626
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492295"
---
# <a name="concurrentpriorityqueue-class"></a>concurrent_priority_queue クラス

`concurrent_priority_queue` クラスは、複数のスレッドが項目を同時にプッシュおよびポップできるようにするコンテナーです。 項目は優先順位の順にポップされます。この優先順位は、テンプレート引数として指定されたファンクタによって決まります。

## <a name="syntax"></a>構文

```
template <typename T,
    typename _Compare= std::less<T>,
    typename _Ax = std::allocator<T>
>,
    typename _Ax = std::allocator<T>> class concurrent_priority_queue;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
優先順位キューに格納される要素のデータ型。

*_Compare*<br/>
優先順位キューでは、次の相対順序を決定する並べ替えキーとして 2 つの要素の値を比較できる関数オブジェクトの型。 この引数は省略可能であり、既定値は二項述語 `less<T>` です。

*_Ax*<br/>
割り当てと、同時実行の優先順位キューのメモリの解放に関する詳細をカプセル化する格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `allocator<T>` です。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`allocator_type`|同時実行の優先順位キューのアロケーター クラスを表す型。|
|`const_reference`|同時実行の優先順位キューに格納されている型の要素への const 参照を表す型。|
|`reference`|同時実行の優先順位キューに格納されている型の要素への参照を表す型。|
|`size_type`|同時実行の優先順位キュー内の要素の数をカウントする型。|
|`value_type`|同時実行の優先順位キューに格納されているデータ型を表す型。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[concurrent_priority_queue](#ctor)|オーバーロードされます。 同時実行の優先度のキューを作成します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[clear](#clear)|同時実行の優先度のすべての要素を消去します。 このメソッドはコンカレンシー セーフではありません。|
|[empty](#empty)|テスト時に、同時実行の優先順位キューが空の場合、このメソッドが呼び出されます。 このメソッドはコンカレンシー セーフです。|
|[get_allocator](#get_allocator)|同時実行の優先順位キューの構築に使用するアロケーターのコピーを返します。 このメソッドはコンカレンシー セーフです。|
|[push](#push)|オーバーロードされます。 同時実行の優先順位キューに要素を追加します。 このメソッドはコンカレンシー セーフです。|
|[size](#size)|同時実行の優先順位キュー内の要素の数を返します。 このメソッドはコンカレンシー セーフです。|
|[swap](#swap)|2 つの同時実行の優先順位キューの内容を交換します。 このメソッドはコンカレンシー セーフではありません。|
|[try_pop](#try_pop)|削除し、キューが空でない場合は、キューから最高の優先順位の要素を返します。 このメソッドはコンカレンシー セーフです。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator=](#operator_eq)|オーバーロードされます。 別の `concurrent_priority_queue` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドはコンカレンシー セーフではありません。|

## <a name="remarks"></a>Remarks

詳細については、`concurrent_priority_queue`クラスを参照してください[並列コンテナーとオブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`concurrent_priority_queue`

## <a name="requirements"></a>必要条件

**ヘッダー:** concurrent_priority_queue.h

**名前空間:** concurrency

##  <a name="clear"></a> オフ

同時実行の優先度のすべての要素を消去します。 このメソッドはコンカレンシー セーフではありません。

```
void clear();
```

### <a name="remarks"></a>Remarks

`clear` 同時実行セーフではありません。 他のスレッドがメソッドを呼び出していない、同時実行の優先順位キューにこのメソッドを呼び出すとすることを確認する必要があります。 `clear` メモリを解放しません。

##  <a name="ctor"></a> concurrent_priority_queue

同時実行の優先度のキューを作成します。

```
explicit concurrent_priority_queue(
    const allocator_type& _Al = allocator_type());

explicit concurrent_priority_queue(
    size_type _Init_capacity,
    const allocator_type& _Al = allocator_type());

template<typename _InputIterator>
concurrent_priority_queue(_InputIterator _Begin,
    _InputIterator _End,
    const allocator_type& _Al = allocator_type());

concurrent_priority_queue(
    const concurrent_priority_queue& _Src);

concurrent_priority_queue(
    const concurrent_priority_queue& _Src,
    const allocator_type& _Al);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src);

concurrent_priority_queue(
    concurrent_priority_queue&& _Src,
    const allocator_type& _Al);
```

### <a name="parameters"></a>パラメーター

*_InputIterator*<br/>
入力反復子の型。

*_Al*<br/>
このオブジェクトに対して使用するアロケーター クラス。

*_Init_capacity*<br/>
`concurrent_priority_queue` オブジェクトの初期容量。

*開始 (_b)*<br/>
コピーする要素範囲内の最初の要素の位置。

*(_E)*<br/>
コピーする要素範囲を超える最初の要素の位置。

*_Src*<br/>
要素のコピー元または移動元の `concurrent_priority_queue` オブジェクト。

### <a name="remarks"></a>Remarks

すべてのコンス トラクターは、アロケーター オブジェクトを格納`_Al`優先順位キューを初期化します。

最初のコンス トラクターは、空の初期の優先順位キューを指定し、アロケーターを指定します。

2 番目のコンス トラクターは、初期容量を使用した優先順位キューを指定します`_Init_capacity`し必要に応じて、アロケーターを指定します。

3 番目のコンス トラクターは、反復子の範囲で指定された値を指定する [ `_Begin`、 `_End`) し、必要に応じて、アロケーターを指定します。

4 番目と 5 番目のコンス トラクターは、優先順位キューのコピーを指定`_Src`します。

6 番目と 7 番目のコンス トラクターは、優先順位キューの移動を指定`_Src`します。

##  <a name="empty"></a> 空

テスト時に、同時実行の優先順位キューが空の場合、このメソッドが呼び出されます。 このメソッドはコンカレンシー セーフです。

```
bool empty() const;
```

### <a name="return-value"></a>戻り値

**true**場合は、関数が呼び出された時点で、優先順位キューが空**false**それ以外の場合。

##  <a name="get_allocator"></a> get_allocator

同時実行の優先順位キューの構築に使用するアロケーターのコピーを返します。 このメソッドはコンカレンシー セーフです。

```
allocator_type get_allocator() const;
```

### <a name="return-value"></a>戻り値

構築に使用するアロケーターのコピー、`concurrent_priority_queue`オブジェクト。

##  <a name="operator_eq"></a> 演算子 =

別の `concurrent_priority_queue` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドはコンカレンシー セーフではありません。

```
concurrent_priority_queue& operator= (const concurrent_priority_queue& _Src);

concurrent_priority_queue& operator= (concurrent_priority_queue&& _Src);
```

### <a name="parameters"></a>パラメーター

*_Src*<br/>
ソース `concurrent_priority_queue` オブジェクト。

### <a name="return-value"></a>戻り値

この `concurrent_priority_queue` オブジェクトへの参照。

##  <a name="push"></a> プッシュ

同時実行の優先順位キューに要素を追加します。 このメソッドはコンカレンシー セーフです。

```
void push(const value_type& _Elem);

void push(value_type&& _Elem);
```

### <a name="parameters"></a>パラメーター

*_Elem*<br/>
同時実行の優先順位キューに追加する要素。

##  <a name="size"></a> サイズ

同時実行の優先順位キュー内の要素の数を返します。 このメソッドはコンカレンシー セーフです。

```
size_type size() const;
```

### <a name="return-value"></a>戻り値

この要素の数`concurrent_priority_queue`オブジェクト。

### <a name="remarks"></a>Remarks

返されるサイズ、関数の呼び出しによって追加されたすべての要素を含めることが保証されます`push`します。 ただし、保留中の同時実行操作の結果は反映されません可能性があります。

##  <a name="swap"></a> スワップ

2 つの同時実行の優先順位キューの内容を交換します。 このメソッドはコンカレンシー セーフではありません。

```
void swap(concurrent_priority_queue& _Queue);
```

### <a name="parameters"></a>パラメーター

*_Fronty*<br/>
`concurrent_priority_queue`コンテンツを交換するオブジェクト。

##  <a name="try_pop"></a> try_pop

削除し、キューが空でない場合は、キューから最高の優先順位の要素を返します。 このメソッドはコンカレンシー セーフです。

```
bool try_pop(reference _Elem);
```

### <a name="parameters"></a>パラメーター

*_Elem*<br/>
キューが空でない場合に、最高の優先順位の要素で設定される変数への参照。

### <a name="return-value"></a>戻り値

**true**場合は、値がポップされ、 **false**それ以外の場合。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)

