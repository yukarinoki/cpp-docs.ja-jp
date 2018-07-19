---
title: timer クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
dev_langs:
- C++
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8372e32b408b97a6ac652b0ff2ff5cc19de69b54
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693225"
---
# <a name="timer-class"></a>timer クラス
`timer` メッセージング ブロックは単一のターゲットを持つ `source_block` であり、指定された時間の経過後か、特定の間隔で、メッセージをターゲットに送信することができます。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 このブロックの出力メッセージのペイロードの種類。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[timer](#ctor)|オーバーロードされます。 構築、`timer`メッセージング ブロックで、指定した間隔の後に、特定のメッセージが起動されます。|  
|[~ timer デストラクター](#dtor)|破棄、`timer`メッセージング ブロックです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[pause](#pause)|停止、`timer`メッセージング ブロックです。 場合は、繰り返し`timer`ブロックをメッセージング、再起動すると、後続`start()`呼び出します。 – 非繰り返しタイマーの場合、この同じ効果として、`stop`を呼び出します。|  
|[start](#start)|開始、`timer`メッセージング ブロックです。 これまでのミリ秒数の指定が呼び出されると、指定した値が反映されるとダウン ストリーム、`message`です。|  
|[stop](#stop)|停止、`timer`メッセージング ブロックです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れる`timer`メッセージング ブロックで、呼び出し元に所有権を転送します。|  
|[consume_message](#consume_message)|によって以前に提供メッセージを使用して、`timer`所有権を転送する、呼び出し元に、ターゲットによって予約されているとします。|  
|[link_target_notification](#link_target_notification)|新しいターゲットがこれにリンクされていることを通知するコールバック`timer`メッセージング ブロックです。|  
|[propagate_to_any_targets](#propagate_to_any_targets)|によって生成されたメッセージを提供しようとする、`timer`すべてのリンクのターゲットをブロックします。|  
|[release_message](#release_message)|以前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|  
|[reserve_message](#reserve_message)|これによって以前に提供メッセージを予約`timer`メッセージング ブロックです。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|  
|[resume_propagation](#resume_propagation)|伝達は、予約が解放された後に再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 [source_block](source-block-class.md)  
  
 `timer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="accept_message"></a> accept_message 

 これによって提供されたメッセージを受け入れる`timer`メッセージング ブロックで、呼び出し元に所有権を転送します。  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`呼び出し元がの所有権をオブジェクトします。  
  
##  <a name="consume_message"></a> consume_message 

 によって以前に提供メッセージを使用して、`timer`所有権を転送する、呼び出し元に、ターゲットによって予約されているとします。  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`使用されているオブジェクトします。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`呼び出し元がの所有権をオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 ような`accept`への呼び出し前に常に、`reserve`です。  
  
##  <a name="link_target_notification"></a> link_target_notification 

 新しいターゲットがこれにリンクされていることを通知するコールバック`timer`メッセージング ブロックです。  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 新しくリンクされたターゲットへのポインター。  
  
##  <a name="pause"></a> 一時停止 

 停止、`timer`メッセージング ブロックです。 場合は、繰り返し`timer`ブロックをメッセージング、再起動すると、後続`start()`呼び出します。 – 非繰り返しタイマーの場合、この同じ効果として、`stop`を呼び出します。  
  
```
void pause();
```  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 によって生成されたメッセージを提供しようとする、`timer`すべてのリンクのターゲットをブロックします。  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```  
  
##  <a name="release_message"></a> release_message 

 以前のメッセージの予約を解放します。  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
##  <a name="reserve_message"></a> reserve_message 

 これによって以前に提供メッセージを予約`timer`メッセージング ブロックです。  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`オブジェクトの中に予約されています。  
  
### <a name="return-value"></a>戻り値  
 `true` 場合は、メッセージが正常に予約された、`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 後に`reserve`と呼ばれる場合は、返された場合`true`か、`consume`または`release`かかるか、メッセージの所有権を解放を呼び出す必要があります。  
  
##  <a name="resume_propagation"></a> resume_propagation 

 伝達は、予約が解放された後に再開します。  
  
```
virtual void resume_propagation();
```  
  
##  <a name="start"></a> 開始 

 開始、`timer`メッセージング ブロックです。 これまでのミリ秒数の指定が呼び出されると、指定した値が反映されるとダウン ストリーム、`message`です。  
  
```
void start();
```  
  
##  <a name="stop"></a> 停止 

 停止、`timer`メッセージング ブロックです。  
  
```
void stop();
```  
  
##  <a name="ctor"></a> タイマー 

 構築、`timer`メッセージング ブロックで、指定した間隔の後に、特定のメッセージが起動されます。  
  
```
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Ms`  
 ダウン ストリームに伝達する指定したメッセージに対する開始呼び出しの後までの経過時間 (ミリ秒) の数。  
  
 `value`  
 タイマーが経過すると下流伝達される値です。  
  
 `_PTarget`  
 タイマーがメッセージを伝達するターゲット。  
  
 `_Repeating`  
 True の場合は、タイマーを定期的に起動を示します。 各`_Ms`(ミリ秒)。  
  
 `_Scheduler`  
 `Scheduler`オブジェクトの反映タスクを内部で、`timer`メッセージング ブロックがスケジュールされているがスケジュールされています。  
  
 `_ScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `timer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 指定しない場合、ランタイムは、既定のスケジューラを使用して、`_Scheduler`または`_ScheduleGroup`パラメーター。  
  
##  <a name="dtor"></a> ~ タイマー 

 破棄、`timer`メッセージング ブロックです。  
  
```
~timer();
```  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
