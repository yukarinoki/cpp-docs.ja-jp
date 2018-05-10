---
title: ordered_message_processor クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ordered_message_processor
- AGENTS/concurrency::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::ordered_message_processor
- AGENTS/concurrency::ordered_message_processor::async_send
- AGENTS/concurrency::ordered_message_processor::initialize
- AGENTS/concurrency::ordered_message_processor::initialize_batched_processing
- AGENTS/concurrency::ordered_message_processor::sync_send
- AGENTS/concurrency::ordered_message_processor::wait
- AGENTS/concurrency::ordered_message_processor::process_incoming_message
dev_langs:
- C++
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27dfb6c1a64d3a4e9df24f3966ec89db1dfbe10c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="orderedmessageprocessor-class"></a>ordered_message_processor クラス
`ordered_message_processor` は、メッセージ ブロックがメッセージを受け取った順序で処理できるようにする `message_processor` です。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class ordered_message_processor : public message_processor<T>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 プロセッサによって処理されるメッセージのペイロードの種類。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`type`|型の別名`T`です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ordered_message_processor](#ctor)|`ordered_message_processor` オブジェクトを構築します。|  
|[~ ordered_message_processor デストラクター](#dtor)|`ordered_message_processor` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[async_send](#async_send)|非同期的にメッセージをキューに登録しがまだ実行されている場合に、処理タスクを開始します。 (上書き[message_processor::async_send](message-processor-class.md#async_send))。|  
|[initialize](#initialize)|初期化、`ordered_message_processor`適切なコールバック関数、スケジューラ、およびスケジュール グループを持つオブジェクト。|  
|[initialize_batched_processing](#initialize_batched_processing)|バッチ処理されたメッセージの処理を初期化します。|  
|[sync_send](#sync_send)|同期的にメッセージをキューに登録しがまだ実行されている場合に、処理タスクを開始します。 (上書き[message_processor::sync_send](message-processor-class.md#sync_send))。|  
|[wait](#wait)|すべての非同期処理タスクのブロックを破棄する前に完了する時間であるかどうかを確認するメッセージ ブロックのデストラクターで使用されるプロセッサ固有のスピン待機します。 (上書き[message_processor::wait](message-processor-class.md#wait))。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|非同期的に呼び出される処理関数です。 メッセージをデキューし、それらの処理を開始します。 (上書き[message_processor::process_incoming_message](message-processor-class.md#process_incoming_message))。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [message_processor](message-processor-class.md)  
  
 `ordered_message_processor`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="async_send"></a> async_send 

 非同期的にメッセージをキューに登録しがまだ実行されている場合に、処理タスクを開始します。  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 メッセージへのポインター。  
  
##  <a name="initialize"></a> 初期化します。 

 初期化、`ordered_message_processor`適切なコールバック関数、スケジューラ、およびスケジュール グループを持つオブジェクト。  
  
```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PScheduler`  
 軽量タスクのスケジューリングに使用されるスケジューラへのポインター。  
  
 `_PScheduleGroup`  
 軽量タスクのスケジューリングに使用する、スケジュール グループへのポインター。  
  
 `_Handler`  
 コールバック中に呼び出されるハンドラー ファンクタ。  
  
##  <a name="initialize_batched_processing"></a> initialize_batched_processing 

 バッチ処理されたメッセージの処理を初期化します。  
  
```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Processor`  
 プロセッサ ファンクタ コールバック中に呼び出されます。  
  
 `_Propagator`  
 伝達子ファンクタ コールバック中に呼び出されます。  
  
##  <a name="ctor"></a> ordered_message_processor 

 `ordered_message_processor` オブジェクトを構築します。  
  
```
ordered_message_processor();
```  
  
### <a name="remarks"></a>コメント  
 これは、`ordered_message_processor`までの非同期的または同期のハンドラーをスケジュールできませんが、`initialize`関数が呼び出されます。  
  
##  <a name="dtor"></a> ~ordered_message_processor 

 `ordered_message_processor` オブジェクトを破棄します。  
  
```
virtual ~ordered_message_processor();
```  
  
### <a name="remarks"></a>コメント  
 プロセッサを破棄する前にすべての未処理の非同期操作を待機します。  
  
##  <a name="process_incoming_message"></a> process_incoming_message 

 非同期的に呼び出される処理関数です。 メッセージをデキューし、それらの処理を開始します。  
  
```
virtual void process_incoming_message();
```  
  
##  <a name="sync_send"></a> sync_send 

 同期的にメッセージをキューに登録しがまだ実行されている場合に、処理タスクを開始します。  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 メッセージへのポインター。  
  
##  <a name="wait"></a> 待機 

 すべての非同期処理タスクのブロックを破棄する前に完了する時間であるかどうかを確認するメッセージ ブロックのデストラクターで使用されるプロセッサ固有のスピン待機します。  
  
```
virtual void wait();
```  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
