---
title: concurrent_queue クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- concurrent_queue class
ms.assetid: c2218996-d0ea-40e9-b002-e9a15b085f51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a9a3ee82b8b81532b4e63f080ad321a93725ce41
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="concurrentqueue-class"></a>concurrent_queue クラス
`concurrent_queue` クラスは、キューの要素に先入れ先出し方式でアクセスできるようにするシーケンス コンテナー クラスです。 これを使用すると、`push`、`try_pop` などの特定の同時実行セーフな操作を実行できます。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 キューに格納される要素のデータ型。  
  
 `_Ax`  
 割り当てとこの同時実行のキューのメモリの解放に関する詳細をカプセル化する格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `allocator<T>` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`allocator_type`|同時実行のキューのアロケーター クラスを表す型。|  
|`const_iterator`|非スレッド セーフを表す型`const`同時実行のキュー内の要素に対する反復子。|  
|`const_reference`|参照を提供する型、`const`要素を読み取りおよび実行する同時実行のキューに格納されている`const`操作します。|  
|`difference_type`|同時実行のキュー内の 2 つの要素間の符号付きの距離を提供する型。|  
|`iterator`|同時実行のキュー内の要素に対する非スレッド セーフな反復子を表す型。|  
|`reference`|同時実行のキューに格納されている要素への参照を提供する型。|  
|`size_type`|同時実行のキュー内の要素の数をカウントする型。|  
|`value_type`|同時実行のキューに格納されているデータ型を表す型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[concurrent_queue](#ctor)|オーバーロードされます。 同時実行のキューを作成します。|  
|[~ concurrent_queue デストラクター](#dtor)|同時実行のキューを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[clear](#clear)|破棄、同時実行のキューをクリア現在キューに格納された要素。 このメソッドは同時実行セーフではありません。|  
|[empty](#empty)|現時点では同時実行のキューは空かどうかをこのメソッドが呼び出されます。 このメソッドは同時実行セーフです。|  
|[get_allocator](#get_allocator)|同時実行のキューを構築するために使用されるアロケーターのコピーを返します。 このメソッドは同時実行セーフです。|  
|[push](#push)|オーバーロードされます。 同時実行のキューの末尾にある項目をエンキューします。 このメソッドは同時実行セーフです。|  
|[try_pop](#try_pop)|1 つが利用可能な場合は、キューから項目をデキューします。 このメソッドは同時実行セーフです。|  
|[unsafe_begin](#unsafe_begin)|オーバーロードされます。 型の反復子を返します`iterator`または`const_iterator`同時実行のキューの先頭にします。 このメソッドは同時実行セーフではありません。|  
|[unsafe_end](#unsafe_end)|オーバーロードされます。 型の反復子を返します`iterator`または`const_iterator`同時実行のキューの末尾にします。 このメソッドは同時実行セーフではありません。|  
|[unsafe_size](#unsafe_size)|キュー内の項目数を返します。 このメソッドは同時実行セーフではありません。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[並列コンテナーと並列オブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `concurrent_queue`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concurrent_queue.h  
  
 **名前空間:** concurrency  
  
##  <a name="clear"></a> オフ 

 破棄、同時実行のキューをクリア現在キューに格納された要素。 このメソッドは同時実行セーフではありません。  
  
```
void clear();
```  
  
##  <a name="ctor"></a> concurrent_queue 

 同時実行のキューを作成します。  
  
```
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
 `_InputIterator`  
 値の範囲を指定する入力反復子の型。  
  
 `_Al`  
 このオブジェクトに対して使用するアロケーター クラス。  
  
 `_OtherQ`  
 要素のコピー元または移動元の `concurrent_queue` オブジェクト。  
  
 `_Begin`  
 コピーする要素範囲内の最初の要素の位置。  
  
 `_End`  
 コピーする要素範囲を超える最初の要素の位置。  
  
### <a name="remarks"></a>コメント  
 すべてのコンス トラクターは、アロケーター オブジェクトを格納`_Al`キューを初期化します。  
  
 最初のコンス トラクターは、空の初期キューを指定し、使用するアロケーターの型を明示的に指定します。  
  
 2 番目のコンス トラクターは、同時実行のキューのコピーを指定する`_OtherQ`です。  
  
 3 番目のコンス トラクターは、同時実行のキューの移動を指定する`_OtherQ`です。  
  
 4 番目のコンス トラクターは、反復子の範囲で指定された値を指定する [ `_Begin`、 `_End`)。  
  
##  <a name="dtor"></a> ~concurrent_queue 

 同時実行のキューを破棄します。  
  
```
~concurrent_queue();
```  
  
##  <a name="empty"></a> 空 

 現時点では同時実行のキューは空かどうかをこのメソッドが呼び出されます。 このメソッドは同時実行セーフです。  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true` 調査した時点で同時実行のキューが空場合、`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 このメソッドは同時実行セーフでは、メソッドの呼び出しに関して`push`、 `try_pop`、および`empty`、返される値可能性がありますいない正しい時では、呼び出し元スレッドで検査されることです。  
  
##  <a name="get_allocator"></a> get_allocator 

 同時実行のキューを構築するために使用されるアロケーターのコピーを返します。 このメソッドは同時実行セーフです。  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行のキューを構築するために使用されるアロケーターのコピー。  
  
##  <a name="push"></a> プッシュ 

 同時実行のキューの末尾にある項目をエンキューします。 このメソッドは同時実行セーフです。  
  
```
void push(const T& _Src);

void push(T&& _Src);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Src`  
 キューに追加する項目。  
  
### <a name="remarks"></a>コメント  
 `push` 同時実行セーフですが、メソッドの呼び出しに関して`push`、 `try_pop`、および`empty`です。  
  
##  <a name="try_pop"></a> try_pop 

 1 つが利用可能な場合は、キューから項目をデキューします。 このメソッドは同時実行セーフです。  
  
```
bool try_pop(T& _Dest);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Dest`  
 キューから取り出された項目を保存する場所への参照。  
  
### <a name="return-value"></a>戻り値  
 `true` 項目が正常にキューから取り出された場合`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 項目が正常にキューから取り出された場合、パラメーター `_Dest` dequeued の値を受け取るキューに保持されている元の値は破棄され、この関数を返します`true`です。 かどうか、キューから削除するアイテムがなかった、この関数を返します`false`のブロックとの内容を行わない限り、`_Dest`パラメーターが定義されていません。  
  
 `try_pop` 同時実行セーフですが、メソッドの呼び出しに関して`push`、 `try_pop`、および`empty`です。  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 型の反復子を返します`iterator`または`const_iterator`同時実行のキューの先頭にします。 このメソッドは同時実行セーフではありません。  
  
```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`iterator`または`const_iterator`の同時実行のキュー オブジェクトの先頭にします。  
  
### <a name="remarks"></a>コメント  
 反復子の`concurrent_queue`クラスは、主にするためのものをデバッグする場合は低速、およびイテレーションが他のキューの操作に対して同時実行セーフではありません。  
  
##  <a name="unsafe_end"></a> unsafe_end 

 型の反復子を返します`iterator`または`const_iterator`同時実行のキューの末尾にします。 このメソッドは同時実行セーフではありません。  
  
```
iterator unsafe_end();

const_iterator unsafe_end() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`iterator`または`const_iterator`同時実行のキューの末尾にします。  
  
### <a name="remarks"></a>コメント  
 反復子の`concurrent_queue`クラスは、主にするためのものをデバッグする場合は低速、およびイテレーションが他のキューの操作に対して同時実行セーフではありません。  
  
##  <a name="unsafe_size"></a> unsafe_size 

 キュー内の項目数を返します。 このメソッドは同時実行セーフではありません。  
  
```
size_type unsafe_size() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行のキューのサイズ。  
  
### <a name="remarks"></a>コメント  
 `unsafe_size` 同時実行セーフではないと、メソッドを呼び出したのと同時に呼び出された場合、正しくない結果を生じることができます`push`、 `try_pop`、および`empty`です。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
