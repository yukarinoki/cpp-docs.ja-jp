---
title: single_assignment クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- single_assignment
- AGENTS/concurrency::single_assignment
- AGENTS/concurrency::single_assignment::single_assignment
- AGENTS/concurrency::single_assignment::has_value
- AGENTS/concurrency::single_assignment::value
- AGENTS/concurrency::single_assignment::accept_message
- AGENTS/concurrency::single_assignment::consume_message
- AGENTS/concurrency::single_assignment::link_target_notification
- AGENTS/concurrency::single_assignment::propagate_message
- AGENTS/concurrency::single_assignment::propagate_to_any_targets
- AGENTS/concurrency::single_assignment::release_message
- AGENTS/concurrency::single_assignment::reserve_message
- AGENTS/concurrency::single_assignment::resume_propagation
- AGENTS/concurrency::single_assignment::send_message
dev_langs:
- C++
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bacbdaa4af141101863b4d6d81d114d43aced9f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="singleassignment-class"></a>single_assignment クラス
`single_assignment` メッセージング ブロックは、一度だけ書き込むことができる `propagator_block` を 1 つ格納できる、複数のターゲットと複数のソースを持つ順序付けられた `message` です。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージのペイロードの型が格納され、バッファーによって反映されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[single_assignment](#ctor)|オーバーロードされます。 構築、`single_assignment`メッセージング ブロックです。|  
|[~ single_assignment デストラクター](#dtor)|破棄、`single_assignment`メッセージング ブロックです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[has_value](#has_value)|チェックするかどうかこの`single_assignment`メッセージング ブロックはまだ初期化されて、値を使用します。|  
|[value](#value)|格納されているメッセージの現在のペイロードへの参照を取得、`single_assignment`メッセージング ブロックです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れる`single_assignment`メッセージング ブロックで、呼び出し元に、メッセージのコピーを取得します。|  
|[consume_message](#consume_message)|によって以前に提供メッセージを使用して、`single_assignment`呼び出し元に、メッセージのコピーを返す、ターゲットによって予約されているとします。|  
|[link_target_notification](#link_target_notification)|新しいターゲットがこれにリンクされていることを通知するコールバック`single_assignment`メッセージング ブロックです。|  
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`ブロックをこの`single_assignment`メッセージング ブロックです。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[propagate_to_any_targets](#propagate_to_any_targets)|場所、`message _PMessage`この`single_assignment`ブロックのメッセージングおよびすべてのリンクのターゲットに提供します。|  
|[release_message](#release_message)|以前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|  
|[reserve_message](#reserve_message)|これによって以前に提供メッセージを予約`single_assignment`メッセージング ブロックです。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|  
|[resume_propagation](#resume_propagation)|伝達は、予約が解放された後に再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|  
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`ブロックをこの`single_assignment`メッセージング ブロックです。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。|  
  
## <a name="remarks"></a>コメント  
 A`single_assignment`メッセージング ブロックは、各ターゲットにそのメッセージのコピーを伝達します。  
  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `single_assignment`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="accept_message"></a> accept_message 

 これによって提供されたメッセージを受け入れる`single_assignment`メッセージング ブロックで、呼び出し元に、メッセージのコピーを取得します。  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`呼び出し元がの所有権をオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 `single_assignment`現在保持しているメッセージの所有権を譲渡するのではなく、メッセージング ブロックをターゲットにメッセージのコピーを返します。  
  
##  <a name="consume_message"></a> consume_message 

 によって以前に提供メッセージを使用して、`single_assignment`呼び出し元に、メッセージのコピーを返す、ターゲットによって予約されているとします。  
  
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
  
##  <a name="has_value"></a> has_value 

 チェックするかどうかこの`single_assignment`メッセージング ブロックはまだ初期化されて、値を使用します。  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true` ブロックは、値を受け取っている場合`false`それ以外の場合。  
  
##  <a name="link_target_notification"></a> link_target_notification 

 新しいターゲットがこれにリンクされていることを通知するコールバック`single_assignment`メッセージング ブロックです。  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 新しくリンクされたターゲットへのポインター。  
  
##  <a name="propagate_message"></a> propagate_message 

 メッセージを非同期的に渡す、`ISource`ブロックをこの`single_assignment`メッセージング ブロックです。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)のメッセージを行うには、対象の決定を示す値。  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 場所、 `message` `_PMessage`この`single_assignment`ブロックのメッセージングおよびすべてのリンクのターゲットに提供します。  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 ポインター、`message`この`single_assignment`メッセージング ブロックがの所有権を取得します。  
  
##  <a name="release_message"></a> release_message 

 以前のメッセージの予約を解放します。  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
##  <a name="reserve_message"></a> reserve_message 

 これによって以前に提供メッセージを予約`single_assignment`メッセージング ブロックです。  
  
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
  
##  <a name="send_message"></a> send_message 

 メッセージを同期的に渡す、`ISource`ブロックをこの`single_assignment`メッセージング ブロックです。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)のメッセージを行うには、対象の決定を示す値。  
  
##  <a name="ctor"></a> single_assignment 

 構築、`single_assignment`メッセージング ブロックです。  
  
```
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filter`  
 提供されたメッセージを受け付けるかどうかを判断するフィルター関数。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `single_assignment` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `single_assignment` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 型`filter_method`シグネチャを持つファンクターは、`bool (T const &)`これは、これによって呼び出されます。`single_assignment`メッセージング ブロックを、提供されたメッセージを受け入れる必要がありますかどうかを判断します。  
  
##  <a name="dtor"></a> ~single_assignment 

 破棄、`single_assignment`メッセージング ブロックです。  
  
```
~single_assignment();
```  
  
##  <a name="value"></a> 値 

 格納されているメッセージの現在のペイロードへの参照を取得、`single_assignment`メッセージング ブロックです。  
  
```
T const& value();
```  
  
### <a name="return-value"></a>戻り値  
 格納されたメッセージのペイロード。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、メッセージが現在格納されていない場合、メッセージが到着するまでに待機、`single_assignment`メッセージング ブロックです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [overwrite_buffer クラス](overwrite-buffer-class.md)   
 [unbounded_buffer クラス](unbounded-buffer-class.md)

