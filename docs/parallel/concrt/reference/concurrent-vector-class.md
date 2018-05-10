---
title: concurrent_vector クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- concurrent_vector class
ms.assetid: a217b4ac-af2b-4d41-94eb-09a75ee28622
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e120e072fb3f56788cbf39fbbc3887f5c816f4ef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="concurrentvector-class"></a>concurrent_vector クラス
`concurrent_vector` クラスは、任意の要素にランダムにアクセスできるようにするシーケンス コンテナー クラスです。 これを使用すると、同時実行セーフな追加、要素アクセス、反復子アクセス、および反復子走査の各操作を実行できます。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T, class _Ax>
class concurrent_vector: protected details::_Allocator_base<T,
    _Ax>,
 private details::_Concurrent_vector_base_v4;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 ベクトルに格納される要素のデータ型。  
  
 `_Ax`  
 同時実行ベクターのメモリの割り当てと解放に関する詳細をカプセル化する、格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `allocator<T>` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`allocator_type`|同時実行ベクターのアロケーター クラスを表す型。|  
|`const_iterator`|読み取ることができるランダム アクセス反復子を提供する型、`const`同時実行ベクター内の要素。|  
|`const_pointer`|ポインターを提供する型、`const`同時実行ベクター内の要素。|  
|`const_reference`|参照を提供する型、`const`要素を読み取りおよび実行する同時実行ベクターに格納されている`const`操作します。|  
|`const_reverse_iterator`|読み取るいずれかのことができるランダム アクセス反復子を提供する型`const`同時実行ベクター内の要素。|  
|`difference_type`|同時実行ベクター内の 2 つの要素間の符号付きの距離を提供する型。|  
|`iterator`|同時実行ベクター内の要素を読み取ることができるランダム アクセス反復子を提供する型。 反復子を使用して、要素の変更は、同時実行セーフではないです。|  
|`pointer`|同時実行ベクター内の要素へのポインターを提供する型。|  
|`reference`|同時実行ベクターに格納されている要素への参照を提供する型。|  
|`reverse_iterator`|逆順の同時実行ベクター内の任意の要素を読み取ることができるランダム アクセス反復子を提供する型。 反復子を使用して、要素の変更は、同時実行セーフではないです。|  
|`size_type`|同時実行ベクターの要素の数をカウントする型。|  
|`value_type`|同時実行ベクターに格納されているデータ型を表す型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[concurrent_vector](#ctor)|オーバーロードされます。 同時実行ベクターを構築します。|  
|[~ concurrent_vector デストラクター](#dtor)|すべての要素を消去し、この同時実行ベクターを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[assign](#assign)|オーバーロードされます。 同時実行ベクターの要素を消去し、いずれかを代入`_N`部数`_Item`、または反復子の範囲で指定された値 [ `_Begin`、 `_End`)。 このメソッドは同時実行セーフではありません。|  
|[at](#at)|オーバーロードされます。 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは同時実行セーフの読み取り操作とするように動作を値として、ベクトルを拡大しているときにも`_Index`が、同時実行ベクターのサイズより小さい。|  
|[back](#back)|オーバーロードされます。 または、参照を返します。`const`最後に、同時実行ベクター内の要素を参照します。 同時実行ベクターが空の場合、戻り値は定義されません。 このメソッドは同時実行セーフです。|  
|[begin](#begin)|オーバーロードされます。 型の反復子を返します`iterator`または`const_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。|  
|[capacity](#capacity)|同時実行ベクターがより多くのメモリを割り当てることがなく拡張できる最大サイズを返します。 このメソッドは同時実行セーフです。|  
|[cbegin](#cbegin)|型の反復子を返します`const_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。|  
|[cend](#cend)|型の反復子を返します`const_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。|  
|[clear](#clear)|同時実行ベクターのすべての要素を消去します。 このメソッドは同時実行セーフではありません。|  
|[crbegin](#crbegin)|型の反復子を返します`const_reverse_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。|  
|[crend](#crend)|型の反復子を返します`const_reverse_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。|  
|[empty](#empty)|テスト時に、同時実行ベクターが空の場合、このメソッドが呼び出されます。 このメソッドは同時実行セーフです。|  
|[end](#end)|オーバーロードされます。 型の反復子を返します`iterator`または`const_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。|  
|[front](#front)|オーバーロードされます。 または、参照を返します。 `const` 、同時実行ベクターの最初の要素への参照。 同時実行ベクターが空の場合、戻り値は定義されません。 このメソッドは同時実行セーフです。|  
|[get_allocator](#get_allocator)|同時実行ベクターを構築するために使用されるアロケーターのコピーを返します。 このメソッドは同時実行セーフです。|  
|[grow_by](#grow_by)|オーバーロードされます。 この同時実行ベクターで`_Delta`要素。 このメソッドは同時実行セーフです。|  
|[grow_to_at_least](#grow_to_at_least)|少なくともになるまでこの同時実行ベクターを拡張`_N`要素。 このメソッドは同時実行セーフです。|  
|[max_size](#max_size)|同時実行ベクターに格納できる要素の最大数を返します。 このメソッドは同時実行セーフです。|  
|[push_back](#push_back)|オーバーロードされます。 同時実行ベクターの末尾に指定された項目を追加します。 このメソッドは同時実行セーフです。|  
|[rbegin](#rbegin)|オーバーロードされます。 型の反復子を返します`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。|  
|[rend](#rend)|オーバーロードされます。 型の反復子を返します`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。|  
|[reserve](#reserve)|サイズに、同時実行ベクターを拡張するための十分な領域を割り当てます`_N`を後でより多くのメモリを割り当てる必要はありません。 このメソッドは同時実行セーフではありません。|  
|[resize](#resize)|オーバーロードされます。 要求されたサイズ、削除、または必要に応じて、要素を追加するには、同時実行ベクターのサイズを変更します。 このメソッドは同時実行セーフではありません。|  
|[shrink_to_fit](#shrink_to_fit)|断片化を削減し、メモリ使用量を最適化する同時実行ベクターの内部表現が圧縮されます。 このメソッドは同時実行セーフではありません。|  
|[size](#size)|同時実行ベクターの要素の数を返します。 このメソッドは同時実行セーフです。|  
|[swap](#swap)|2 つの同時実行ベクターのコンテンツを交換します。 このメソッドは同時実行セーフではありません。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator[]](#operator_at)|オーバーロードされます。 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは同時実行セーフ読み取り操作とするように動作を値として、ベクトルを拡大しているときにも`_Index`が、同時実行ベクターのサイズより小さい。|  
|[operator=](#operator_eq)|オーバーロードされます。 別の `concurrent_vector` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。|  
  
## <a name="remarks"></a>コメント  
 詳細については、`concurrent_vector`クラスを参照してください[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `_Concurrent_vector_base_v4`  
  
 `_Allocator_base`  
  
 `concurrent_vector`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concurrent_vector.h  
  
 **名前空間:** concurrency  
  
##  <a name="assign"></a> 割り当てる 

 同時実行ベクターの要素を消去し、いずれかを代入`_N`部数`_Item`、または反復子の範囲で指定された値 [ `_Begin`、 `_End`)。 このメソッドは同時実行セーフではありません。  
  
```
void assign(
    size_type _N,
    const_reference _Item);

template<class _InputIterator>
void assign(_InputIterator _Begin,
    _InputIterator _End);
```  
  
### <a name="parameters"></a>パラメーター  
 `_InputIterator`  
 指定した反復子の型。  
  
 `_N`  
 同時実行ベクターにコピーするアイテムの数。  
  
 `_Item`  
 同時実行ベクターの塗りつぶしに使用される値への参照。  
  
 `_Begin`  
 ソース範囲の最初の要素の反復子。  
  
 `_End`  
 1 つ後ろのソース範囲の最後の要素を反復子。  
  
### <a name="remarks"></a>コメント  
 `assign` 同時実行セーフではありません。 他のスレッドはメソッドを呼び出していない、同時実行ベクターをこのメソッドを呼び出すとを確認する必要があります。  
  
##  <a name="at"></a> で 

 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは同時実行セーフの読み取り操作とするように動作を値として、ベクトルを拡大しているときにも`_Index`が、同時実行ベクターのサイズより小さい。  
  
```
reference at(size_type _Index);

const_reference at(size_type _Index) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 取得する要素のインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置にある項目への参照。  
  
### <a name="remarks"></a>コメント  
 関数のバージョン`at`以外を返す`const`要素への異なるスレッドから同時に書き込みに参照は使用できません。 さまざまな同期オブジェクトは、同時読み取りを同期し、同じデータ要素への書き込み操作を使用してください。  
  
 メソッドをスロー`out_of_range`場合`_Index`より大きいか、同時実行ベクターのサイズに等しいと`range_error`のベクターの破損部分のインデックスがある場合。 ベクターが切断される方法の詳細については、「[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)です。  
  
##  <a name="back"></a> 戻る 

 または、参照を返します。`const`最後に、同時実行ベクター内の要素を参照します。 同時実行ベクターが空の場合、戻り値は定義されません。 このメソッドは同時実行セーフです。  
  
```
reference back();

const_reference back() const;
```  
  
### <a name="return-value"></a>戻り値  
 参照や`const`最後に、同時実行ベクター内の要素を参照します。  
  
##  <a name="begin"></a> 開始 

 型の反復子を返します`iterator`または`const_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`iterator`または`const_iterator`同時実行ベクターの先頭にします。  
  
##  <a name="capacity"></a> 容量 

 同時実行ベクターがより多くのメモリを割り当てることがなく拡張できる最大サイズを返します。 このメソッドは同時実行セーフです。  
  
```
size_type capacity() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行ベクターがより多くのメモリを割り当てることがなく拡張できる最大サイズ。  
  
### <a name="remarks"></a>コメント  
 C++ 標準ライブラリとは異なり`vector`、`concurrent_vector`より多くのメモリを割り当てる場合は、オブジェクトが既存の要素を移動しません。  
  
##  <a name="cbegin"></a> cbegin 

 型の反復子を返します`const_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`const_iterator`同時実行ベクターの先頭にします。  
  
##  <a name="cend"></a> cend 

 型の反復子を返します`const_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`const_iterator`同時実行ベクターの末尾にします。  
  
##  <a name="clear"></a> オフ 

 同時実行ベクターのすべての要素を消去します。 このメソッドは同時実行セーフではありません。  
  
```
void clear();
```  
  
### <a name="remarks"></a>コメント  
 `clear` 同時実行セーフではありません。 他のスレッドはメソッドを呼び出していない、同時実行ベクターをこのメソッドを呼び出すとを確認する必要があります。 `clear` 内部の配列を解放しません。 内部の配列を解放するには、関数を呼び出す`shrink_to_fit`後`clear`です。  
  
##  <a name="ctor"></a> concurrent_vector 

 同時実行ベクターを構築します。  
  
```
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
 `M`  
 ソース ベクターのアロケーターの型。  
  
 `_InputIterator`  
 入力反復子の型。  
  
 `_Al`  
 このオブジェクトに対して使用するアロケーター クラス。  
  
 `_Vector`  
 要素のコピー元または移動元の `concurrent_vector` オブジェクト。  
  
 `_N`  
 `concurrent_vector` オブジェクトの初期容量。  
  
 `_Item`  
 構築されたオブジェクトの要素の値。  
  
 `_Begin`  
 コピーする要素範囲内の最初の要素の位置。  
  
 `_End`  
 コピーする要素範囲を超える最初の要素の位置。  
  
### <a name="remarks"></a>コメント  
 すべてのコンストラクターは、アロケーター オブジェクト `_Al` を格納し、ベクターを初期化します。  
  
 最初のコンス トラクターは、空の初期ベクターを指定し、アロケーターの型を明示的に指定します。 使用されます。  
  
 2 つ目および 3 つ目のコンストラクターは、同時実行ベクター `_Vector` のコピーを指定します。  
  
 4 番目のコンストラクターは、同時実行ベクター `_Vector` の移動を指定します。  
  
 5 番目のコンス トラクターを指定された数の繰り返しを指定します ( `_N`) クラスの既定値の要素の`T`します。  
  
 6 番目のコンス トラクターは、指定の繰り返し ( `_N`) の値の要素`_Item`です。  
  
 最後のコンス トラクターは、反復子の範囲で指定された値を指定します。 [ `_Begin`、 `_End`)。  
  
##  <a name="dtor"></a> ~concurrent_vector 

 すべての要素を消去し、この同時実行ベクターを破棄します。  
  
```
~concurrent_vector();
```  
  
##  <a name="crbegin"></a> crbegin 

 型の反復子を返します`const_reverse_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。  
  
```
const_reverse_iterator crbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`const_reverse_iterator`同時実行ベクターの先頭にします。  
  
##  <a name="crend"></a> crend 

 型の反復子を返します`const_reverse_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。  
  
```
const_reverse_iterator crend() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`const_reverse_iterator`同時実行ベクターの末尾にします。  
  
##  <a name="empty"></a> 空 

 テスト時に、同時実行ベクターが空の場合、このメソッドが呼び出されます。 このメソッドは同時実行セーフです。  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true` 場合は、ベクターが空では、関数が呼び出された時点で`false`それ以外の場合。  
  
##  <a name="end"></a> 終わり 

 型の反復子を返します`iterator`または`const_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`iterator`または`const_iterator`同時実行ベクターの末尾にします。  
  
##  <a name="front"></a> 前面 

 または、参照を返します。 `const` 、同時実行ベクターの最初の要素への参照。 同時実行ベクターが空の場合、戻り値は定義されません。 このメソッドは同時実行セーフです。  
  
```
reference front();

const_reference front() const;
```  
  
### <a name="return-value"></a>戻り値  
 参照や`const`同時実行ベクターの最初の要素への参照。  
  
##  <a name="get_allocator"></a> get_allocator 

 同時実行ベクターを構築するために使用されるアロケーターのコピーを返します。 このメソッドは同時実行セーフです。  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>戻り値  
 構築するために使用されるアロケーターのコピー、`concurrent_vector`オブジェクト。  
  
##  <a name="grow_by"></a> grow_by 

 この同時実行ベクターで`_Delta`要素。 このメソッドは同時実行セーフです。  
  
```
iterator grow_by(
    size_type _Delta);

iterator grow_by(
    size_type _Delta,
    const_reference _Item);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Delta`  
 オブジェクトに追加する要素の数。  
  
 `_Item`  
 新しい要素を初期化する値。  
  
### <a name="return-value"></a>戻り値  
 最初の項目を指す反復子が追加されます。  
  
### <a name="remarks"></a>コメント  
 場合`_Item`が指定されていない、新しい要素が既定で構築します。  
  
##  <a name="grow_to_at_least"></a> grow_to_at_least 

 少なくともになるまでこの同時実行ベクターを拡張`_N`要素。 このメソッドは同時実行セーフです。  
  
```
iterator grow_to_at_least(size_type _N);
```  
  
### <a name="parameters"></a>パラメーター  
 `_N`  
 新しいの最小サイズ、`concurrent_vector`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 インデックス位置にある要素に追加されたシーケンスの先頭を指す反復子`_N`場合、要素は追加されません。  
  
##  <a name="max_size"></a> max_size 

 同時実行ベクターに格納できる要素の最大数を返します。 このメソッドは同時実行セーフです。  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>戻り値  
 要素の最大数、`concurrent_vector`オブジェクトを保持できます。  
  
##  <a name="operator_eq"></a> 演算子 = 

 別の `concurrent_vector` オブジェクトの内容をこのオブジェクトに割り当てます。 このメソッドは同時実行セーフではありません。  
  
```
concurrent_vector& operator= (
    const concurrent_vector& _Vector);

template<class M>
concurrent_vector& operator= (
    const concurrent_vector<T, M>& _Vector);

concurrent_vector& operator= (
    concurrent_vector&& _Vector);
```  
  
### <a name="parameters"></a>パラメーター  
 `M`  
 ソース ベクターのアロケーターの型。  
  
 `_Vector`  
 ソース `concurrent_vector` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `concurrent_vector` オブジェクトへの参照。  
  
##  <a name="operator_at"></a> operator[] 

 同時実行ベクター内の指定したインデックス位置にある要素へのアクセスを提供します。 このメソッドは同時実行セーフ読み取り操作とするように動作を値として、ベクトルを拡大しているときにも`_Index`が、同時実行ベクターのサイズより小さい。  
  
```
reference operator[](size_type _index);

const_reference operator[](size_type _index) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index`  
 取得する要素のインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したインデックス位置にある項目への参照。  
  
### <a name="remarks"></a>コメント  
 バージョン`operator []`以外を返す`const`要素への異なるスレッドから同時に書き込みに参照は使用できません。 さまざまな同期オブジェクトは、同時読み取りを同期し、同じデータ要素への書き込み操作を使用してください。  
  
 チェックを実行することを確認するのにはない境界`_Index`同時実行ベクターに有効なインデックスです。  
  
##  <a name="push_back"></a> push_back 

 同時実行ベクターの末尾に指定された項目を追加します。 このメソッドは同時実行セーフです。  
  
```
iterator push_back(const_reference _Item);

iterator push_back(T&& _Item);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Item`  
 追加する値。  
  
### <a name="return-value"></a>戻り値  
 アイテムを指す反復子が追加されます。  
  
##  <a name="rbegin"></a> rbegin 

 型の反復子を返します`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの先頭にします。 このメソッドは同時実行セーフです。  
  
```
reverse_iterator rbegin();

const_reverse_iterator rbegin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの先頭にします。  
  
##  <a name="rend"></a> rend 

 型の反復子を返します`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの末尾にします。 このメソッドは同時実行セーフです。  
  
```
reverse_iterator rend();

const_reverse_iterator rend() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`reverse_iterator`または`const_reverse_iterator`同時実行ベクターの末尾にします。  
  
##  <a name="reserve"></a> 予約 

 サイズに、同時実行ベクターを拡張するための十分な領域を割り当てます`_N`を後でより多くのメモリを割り当てる必要はありません。 このメソッドは同時実行セーフではありません。  
  
```
void reserve(size_type _N);
```  
  
### <a name="parameters"></a>パラメーター  
 `_N`  
 領域を予約する要素の数。  
  
### <a name="remarks"></a>コメント  
 `reserve` 同時実行セーフではありません。 他のスレッドはメソッドを呼び出していない、同時実行ベクターをこのメソッドを呼び出すとを確認する必要があります。 メソッドが返った後に、同時実行ベクターの容量は、要求された予約を超える可能性があります。  
  
##  <a name="resize"></a> サイズ変更 

 要求されたサイズ、削除、または必要に応じて、要素を追加するには、同時実行ベクターのサイズを変更します。 このメソッドは同時実行セーフではありません。  
  
```
void resize(
    size_type _N);

void resize(
    size_type _N,
    const T& val);
```  
  
### <a name="parameters"></a>パラメーター  
 `_N`  
 Concurrent_vector の新しいサイズ。  
  
 `val`  
 新しい要素の値は、新しいサイズが元のサイズより大きいかどうか、ベクターに追加されます。 値を省略すると、新しいオブジェクトには、その型の既定値は割り当てられます。  
  
### <a name="remarks"></a>コメント  
 コンテナーのサイズが、要求されたサイズよりも小さい場合は、要素は、要求されたサイズに達するまで、ベクターに追加されます。 コンテナー サイズに到達するまで、コンテナーの末尾に近い要素が削除されたコンテナーのサイズが、要求されたサイズよりも大きい場合は、`_N`です。 コンテナーの現在のサイズが要求されたサイズと同じ場合は、何も実行されません。  
  
 `resize` 同時実行安全ではありません。 他のスレッドはメソッドを呼び出していない、同時実行ベクターをこのメソッドを呼び出すとを確認する必要があります。  
  
##  <a name="shrink_to_fit"></a> shrink_to_fit 

 断片化を削減し、メモリ使用量を最適化する同時実行ベクターの内部表現が圧縮されます。 このメソッドは同時実行セーフではありません。  
  
```
void shrink_to_fit();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは内部的に再要素に割り当てますメモリ移動、すべての反復子を無効になります。 `shrink_to_fit` 同時実行セーフではありません。 他のスレッドはメソッドを呼び出していない、同時実行ベクターをこの関数を呼び出すときを確認する必要があります。  
  
##  <a name="size"></a> サイズ 

 同時実行ベクターの要素の数を返します。 このメソッドは同時実行セーフです。  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>戻り値  
 この要素の数`concurrent_vector`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 返されるサイズが、関数への呼び出しにより追加されたすべての要素を含めることが保証`push_back`、またはこのメソッドを呼び出す前に完了した操作を増加します。 ただし、割り当てられている要素を含める場合もが、現在成長のいずれかの呼び出し、同時実行の作成中です。  
  
##  <a name="swap"></a> スワップ 

 2 つの同時実行ベクターのコンテンツを交換します。 このメソッドは同時実行セーフではありません。  
  
```
void swap(concurrent_vector& _Vector);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Vector`  
 `concurrent_vector`でコンテンツを交換するオブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)



