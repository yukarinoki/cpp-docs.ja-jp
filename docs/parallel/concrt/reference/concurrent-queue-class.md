---
title: concurrent_queue クラス |Microsoft Docs
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
ms.openlocfilehash: d211d94903e411db5755bd57873b9d3e33ee54fa
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076490"
---
# <a name="concurrentqueue-class"></a>concurrent_queue クラス
`concurrent_queue` クラスは、キューの要素に先入れ先出し方式でアクセスできるようにするシーケンス コンテナー クラスです。 これを使用すると、`push`、`try_pop` などの特定の同時実行セーフな操作を実行できます。  
  
## <a name="syntax"></a>構文  
  
```
template<typename T, class _Ax>
class concurrent_queue: public ::Concurrency::details::_Concurrent_queue_base_v4;
```  
  
#### <a name="parameters"></a>パラメーター  
*T*<br/>
キューに格納される要素のデータ型。  
  
*_Ax*<br/>
割り当てとこの同時実行キューのメモリの解放に関する詳細をカプセル化する格納されたアロケーター オブジェクトを表す型。 この引数は省略可能であり、既定値は `allocator<T>` です。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`allocator_type`|同時実行のキューのアロケーター クラスを表す型。|  
|`const_iterator`|非スレッド セーフを表す型`const`同時実行キュー内の要素に対する反復子。|  
|`const_reference`|参照を提供する型、`const`読み取りと実行の同時実行のキューに格納されている要素`const`操作。|  
|`difference_type`|同時実行キューの 2 つの要素間の符号付きの距離を提供する型。|  
|`iterator`|同時実行キュー内の要素に対する非スレッド セーフな反復子を表す型。|  
|`reference`|同時実行のキューに格納されている要素への参照を提供する型。|  
|`size_type`|同時実行キュー内の要素の数をカウントする型。|  
|`value_type`|同時実行のキューに格納されているデータ型を表す型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[concurrent_queue](#ctor)|オーバーロードされます。 同時実行のキューを作成します。|  
|[~ concurrent_queue デストラクター](#dtor)|同時実行のキューが破棄されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[clear](#clear)|破棄、同時実行のキューをクリアします。 現在のキューに格納された要素。 このメソッドは同時実行セーフではありません。|  
|[empty](#empty)|現時点で同時実行のキューが空かどうか、このメソッドが呼び出されます。 このメソッドは同時実行セーフです。|  
|[get_allocator](#get_allocator)|同時実行のキューの構築に使用するアロケーターのコピーを返します。 このメソッドは同時実行セーフです。|  
|[push](#push)|オーバーロードされます。 同時実行のキューの末尾にある項目をエンキューします。 このメソッドは同時実行セーフです。|  
|[try_pop](#try_pop)|ある場合は、キューから項目をデキューします。 このメソッドは同時実行セーフです。|  
|[unsafe_begin](#unsafe_begin)|オーバーロードされます。 型の反復子を返します`iterator`または`const_iterator`同時実行のキューの先頭にします。 このメソッドは同時実行セーフではありません。|  
|[unsafe_end](#unsafe_end)|オーバーロードされます。 型の反復子を返します`iterator`または`const_iterator`同時実行のキューの末尾にします。 このメソッドは同時実行セーフではありません。|  
|[unsafe_size](#unsafe_size)|キュー内の項目の数を返します。 このメソッドは同時実行セーフではありません。|  
  
## <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。[並列コンテナーとオブジェクト](../../../parallel/concrt/parallel-containers-and-objects.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `concurrent_queue`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concurrent_queue.h  
  
 **名前空間:** concurrency  
  
##  <a name="clear"></a> オフ 

 破棄、同時実行のキューをクリアします。 現在のキューに格納された要素。 このメソッドは同時実行セーフではありません。  
  
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
*_InputIterator*<br/>
値の範囲を示す入力反復子の型。  
  
*_Al*<br/>
このオブジェクトに対して使用するアロケーター クラス。  
  
*_OtherQ*<br/>
要素のコピー元または移動元の `concurrent_queue` オブジェクト。  
  
*開始 (_b)*<br/>
コピーする要素範囲内の最初の要素の位置。  
  
*(_E)*<br/>
コピーする要素範囲を超える最初の要素の位置。  
  
### <a name="remarks"></a>Remarks  
 すべてのコンス トラクターは、アロケーター オブジェクトを格納`_Al`キューを初期化します。  
  
 最初のコンス トラクターは、空の初期のキューを指定し、使用するアロケーターの型を明示的に指定します。  
  
 2 番目のコンス トラクターには、同時実行のキューのコピーを示す`_OtherQ`します。  
  
 3 番目のコンス トラクターは、同時実行のキューの移動を指定する`_OtherQ`します。  
  
 4 番目のコンス トラクターは、反復子の範囲で指定された値を指定する [ `_Begin`、 `_End`)。  
  
##  <a name="dtor"></a> ~concurrent_queue 

 同時実行のキューが破棄されます。  
  
```
~concurrent_queue();
```  
  
##  <a name="empty"></a> 空 

 現時点で同時実行のキューが空かどうか、このメソッドが呼び出されます。 このメソッドは同時実行セーフです。  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true` しましたが、現時点で、同時実行のキューが空の場合`false`それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは同時実行セーフ メソッドの呼び出しに関して`push`、 `try_pop`、および`empty`、返される値できない可能性があります正しいスレッドの呼び出しによって、調査が時間ごと。  
  
##  <a name="get_allocator"></a> get_allocator 

 同時実行のキューの構築に使用するアロケーターのコピーを返します。 このメソッドは同時実行セーフです。  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行のキューの構築に使用するアロケーターのコピー。  
  
##  <a name="push"></a> プッシュ 

 同時実行のキューの末尾にある項目をエンキューします。 このメソッドは同時実行セーフです。  
  
```
void push(const T& _Src);

void push(T&& _Src);
```  
  
### <a name="parameters"></a>パラメーター  
*_Src*<br/>
キューに追加する項目。  
  
### <a name="remarks"></a>Remarks  
 `push` 同時実行セーフは、メソッドの呼び出しに関して`push`、 `try_pop`、および`empty`します。  
  
##  <a name="try_pop"></a> try_pop 

 ある場合は、キューから項目をデキューします。 このメソッドは同時実行セーフです。  
  
```
bool try_pop(T& _Dest);
```  
  
### <a name="parameters"></a>パラメーター  
*_Dest*<br/>
デキューされる項目を保存する場所への参照。  
  
### <a name="return-value"></a>戻り値  
 `true` 項目が正常にデキューされる場合は`false`それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 項目が正常にデキューされる場合は、パラメーター `_Dest` 、キューから取り出された値を受け取るキューに保持されている元の値を破棄し、この関数を返します`true`します。 かどうか、キューから削除する項目がありません、この関数を返します`false`ブロック、やの内容を行わず、`_Dest`パラメーターが定義されていません。  
  
 `try_pop` 同時実行セーフは、メソッドの呼び出しに関して`push`、 `try_pop`、および`empty`します。  
  
##  <a name="unsafe_begin"></a> unsafe_begin 

 型の反復子を返します`iterator`または`const_iterator`同時実行のキューの先頭にします。 このメソッドは同時実行セーフではありません。  
  
```
iterator unsafe_begin();

const_iterator unsafe_begin() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`iterator`または`const_iterator`同時実行のキュー オブジェクトの先頭にします。  
  
### <a name="remarks"></a>Remarks  
 反復子、`concurrent_queue`クラスは主にデバッグについては、低速、およびイテレーションに関するその他のキュー操作の同時実行セーフでないとします。  
  
##  <a name="unsafe_end"></a> unsafe_end 

 型の反復子を返します`iterator`または`const_iterator`同時実行のキューの末尾にします。 このメソッドは同時実行セーフではありません。  
  
```
iterator unsafe_end();

const_iterator unsafe_end() const;
```  
  
### <a name="return-value"></a>戻り値  
 型の反復子`iterator`または`const_iterator`同時実行のキューの末尾にします。  
  
### <a name="remarks"></a>Remarks  
 反復子、`concurrent_queue`クラスは主にデバッグについては、低速、およびイテレーションに関するその他のキュー操作の同時実行セーフでないとします。  
  
##  <a name="unsafe_size"></a> unsafe_size 

 キュー内の項目の数を返します。 このメソッドは同時実行セーフではありません。  
  
```
size_type unsafe_size() const;
```  
  
### <a name="return-value"></a>戻り値  
 同時実行のキューのサイズ。  
  
### <a name="remarks"></a>Remarks  
 `unsafe_size` 同時実行セーフでないし、メソッドの呼び出しと同時に呼び出された場合、不適切な結果を生成できる`push`、 `try_pop`、および`empty`します。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
