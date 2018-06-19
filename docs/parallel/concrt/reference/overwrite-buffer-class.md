---
title: overwrite_buffer クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- overwrite_buffer
- AGENTS/concurrency::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::has_value
- AGENTS/concurrency::overwrite_buffer::value
- AGENTS/concurrency::overwrite_buffer::accept_message
- AGENTS/concurrency::overwrite_buffer::consume_message
- AGENTS/concurrency::overwrite_buffer::link_target_notification
- AGENTS/concurrency::overwrite_buffer::propagate_message
- AGENTS/concurrency::overwrite_buffer::propagate_to_any_targets
- AGENTS/concurrency::overwrite_buffer::release_message
- AGENTS/concurrency::overwrite_buffer::reserve_message
- AGENTS/concurrency::overwrite_buffer::resume_propagation
- AGENTS/concurrency::overwrite_buffer::send_message
- AGENTS/concurrency::overwrite_buffer::supports_anonymous_source
dev_langs:
- C++
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dccde651898bf5ff0986dc2e577a1d2ee5765e3f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694197"
---
# <a name="overwritebuffer-class"></a>overwrite_buffer クラス
`overwrite_buffer` メッセージング ブロックは、一度に 1 つのメッセージを格納することができる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。 新しいメッセージが与えられると、それまで格納されていたメッセージは上書きされます。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージのペイロードの型が格納され、バッファーによって反映されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[overwrite_buffer](#ctor)|オーバーロードされます。 構築、`overwrite_buffer`メッセージング ブロックです。|  
|[~ overwrite_buffer デストラクター](#dtor)|破棄、`overwrite_buffer`メッセージング ブロックです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[has_value](#has_value)|チェックするかどうかこの`overwrite_buffer`メッセージング ブロックはまだ値。|  
|[value](#value)|格納されているメッセージの現在のペイロードへの参照を取得、`overwrite_buffer`メッセージング ブロックです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れる`overwrite_buffer`メッセージング ブロックで、呼び出し元に、メッセージのコピーを取得します。|  
|[consume_message](#consume_message)|によって以前に提供メッセージを使用して、`overwrite_buffer`ブロックのメッセージングおよび呼び出し元に、メッセージのコピーを返す、ターゲットによって予約されています。|  
|[link_target_notification](#link_target_notification)|新しいターゲットがこれにリンクされていることを通知するコールバック`overwrite_buffer`メッセージング ブロックです。|  
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`ブロックをこの`overwrite_buffer`メッセージング ブロックです。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[propagate_to_any_targets](#propagate_to_any_targets)|場所、`message _PMessage`この`overwrite_buffer`ブロックのメッセージングおよびすべてのリンクのターゲットに提供します。|  
|[release_message](#release_message)|以前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|  
|[reserve_message](#reserve_message)|これによって以前に提供メッセージを予約`overwrite_buffer`メッセージング ブロックです。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|  
|[resume_propagation](#resume_propagation)|伝達は、予約が解放された後に再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|  
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`ブロックをこの`overwrite_buffer`メッセージング ブロックです。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[supports_anonymous_source](#supports_anonymous_source)|上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることができます。 (上書き[itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source))。|  
  
## <a name="remarks"></a>コメント  
 `overwrite_buffer`メッセージング ブロックは、各ターゲットを格納されているメッセージのコピーを伝達します。  
  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `overwrite_buffer`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="accept_message"></a> accept_message 

 これによって提供されたメッセージを受け入れる`overwrite_buffer`メッセージング ブロックで、呼び出し元に、メッセージのコピーを取得します。  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`呼び出し元がの所有権をオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 `overwrite_buffer`現在保持しているメッセージの所有権を譲渡するのではなく、メッセージング ブロックをターゲットにメッセージのコピーを返します。  
  
##  <a name="consume_message"></a> consume_message 

 によって以前に提供メッセージを使用して、`overwrite_buffer`ブロックのメッセージングおよび呼び出し元に、メッセージのコピーを返す、ターゲットによって予約されています。  
  
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

 チェックするかどうかこの`overwrite_buffer`メッセージング ブロックはまだ値。  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>戻り値  
 `true` ブロックは、値を受け取っている場合`false`それ以外の場合。  
  
##  <a name="link_target_notification"></a> link_target_notification 

 新しいターゲットがこれにリンクされていることを通知するコールバック`overwrite_buffer`メッセージング ブロックです。  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 新しくリンクされたターゲットへのポインター。  
  
##  <a name="dtor"></a> ~overwrite_buffer 

 破棄、`overwrite_buffer`メッセージング ブロックです。  
  
```
~overwrite_buffer();
```  
  
##  <a name="ctor"></a> overwrite_buffer 

 構築、`overwrite_buffer`メッセージング ブロックです。  
  
```
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filter`  
 提供されたメッセージを受け付けるかどうかを判断するフィルター関数。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `overwrite_buffer` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `overwrite_buffer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 型`filter_method`シグネチャを持つファンクターは、`bool (T const &)`これは、これによって呼び出されます。`overwrite_buffer`メッセージング ブロックを、提供されたメッセージを受け入れる必要がありますかどうかを判断します。  
  
##  <a name="propagate_message"></a> propagate_message 

 メッセージを非同期的に渡す、`ISource`ブロックをこの`overwrite_buffer`メッセージング ブロックです。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
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

 場所、`message _PMessage`この`overwrite_buffer`ブロックのメッセージングおよびすべてのリンクのターゲットに提供します。  
  
```
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 ポインター、`message`オブジェクトこの`overwrite_buffer`の所有権を取得しました。  
  
### <a name="remarks"></a>コメント  
 このメソッドは現在のメッセージを上書き、`overwrite_buffer`新しく受け入れたメッセージと共に`_PMessage`です。  
  
##  <a name="send_message"></a> send_message 

 メッセージを同期的に渡す、`ISource`ブロックをこの`overwrite_buffer`メッセージング ブロックです。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。  
  
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
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることができます。  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>戻り値  
 `true` ブロックは延期いないために、メッセージを提供します。  
  
##  <a name="release_message"></a> release_message 

 以前のメッセージの予約を解放します。  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
##  <a name="reserve_message"></a> reserve_message 

 これによって以前に提供メッセージを予約`overwrite_buffer`メッセージング ブロックです。  
  
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
  
##  <a name="value"></a> 値 

 格納されているメッセージの現在のペイロードへの参照を取得、`overwrite_buffer`メッセージング ブロックです。  
  
```
T value();
```  
  
### <a name="return-value"></a>戻り値  
 現在格納されているメッセージのペイロード。  
  
### <a name="remarks"></a>コメント  
 格納された値、`overwrite_buffer`このメソッドが戻る後すぐに変更する可能性があります。 このメソッドは、メッセージが現在格納されていない場合、メッセージが到着するまでに待機、`overwrite_buffer`です。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [unbounded_buffer クラス](unbounded-buffer-class.md)   
 [single_assignment クラス](single-assignment-class.md)
