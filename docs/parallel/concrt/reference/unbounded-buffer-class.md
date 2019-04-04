---
title: unbounded_buffer クラス
ms.date: 11/04/2016
f1_keywords:
- unbounded_buffer
- AGENTS/concurrency::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::unbounded_buffer
- AGENTS/concurrency::unbounded_buffer::dequeue
- AGENTS/concurrency::unbounded_buffer::enqueue
- AGENTS/concurrency::unbounded_buffer::accept_message
- AGENTS/concurrency::unbounded_buffer::consume_message
- AGENTS/concurrency::unbounded_buffer::link_target_notification
- AGENTS/concurrency::unbounded_buffer::process_input_messages
- AGENTS/concurrency::unbounded_buffer::propagate_message
- AGENTS/concurrency::unbounded_buffer::propagate_output_messages
- AGENTS/concurrency::unbounded_buffer::release_message
- AGENTS/concurrency::unbounded_buffer::reserve_message
- AGENTS/concurrency::unbounded_buffer::resume_propagation
- AGENTS/concurrency::unbounded_buffer::send_message
- AGENTS/concurrency::unbounded_buffer::supports_anonymous_source
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
ms.openlocfilehash: 1474381a2d1c0947b2428ab4cf0b4683198eef84
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57288145"
---
# <a name="unboundedbuffer-class"></a>unbounded_buffer クラス

`unbounded_buffer` メッセージング ブロックは、メッセージを無制限に格納することができる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。

## <a name="syntax"></a>構文

```
template<
   class             _Type
>
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;
```

#### <a name="parameters"></a>パラメーター

*_Type*<br/>
メッセージのペイロードの型が格納され、バッファーによって反映されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[unbounded_buffer](#ctor)|オーバーロードされます。 構築、`unbounded_buffer`メッセージング ブロックします。|
|[~ unbounded_buffer デストラクター](#dtor)|破棄、`unbounded_buffer`メッセージング ブロックします。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[dequeue](#dequeue)|項目を削除、`unbounded_buffer`メッセージング ブロックします。|
|[enqueue](#enqueue)|項目を追加、`unbounded_buffer`メッセージング ブロックします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れる`unbounded_buffer`メッセージング ブロック、呼び出し元に所有権を転送します。|
|[consume_message](#consume_message)|によって以前に提供されたメッセージを使用して、`unbounded_buffer`メッセージング ブロックと、呼び出し元に所有権を譲渡する、ターゲットによって予約されています。|
|[link_target_notification](#link_target_notification)|この新しいターゲットがリンクされていることを通知するコールバック`unbounded_buffer`メッセージング ブロックします。|
|[process_input_messages](#process_input_messages)|場所、 `message` `_PMessage`この`unbounded_buffer`メッセージング ブロックと、すべてのリンクのターゲットに提供しようとします。|
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`unbounded_buffer`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。|
|[propagate_output_messages](#propagate_output_messages)|場所、 `message` `_PMessage`この`unbounded_buffer`メッセージング ブロックと、すべてのリンクのターゲットに提供しようとします。 (上書き[source_block::propagate_output_messages](source-block-class.md#propagate_output_messages))。|
|[release_message](#release_message)|前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|
|[reserve_message](#reserve_message)|これによって以前に提供されたメッセージを予約`unbounded_buffer`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|
|[resume_propagation](#resume_propagation)|予約が解放された後は、伝達を再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`このブロック`unbounded_buffer`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。|
|[supports_anonymous_source](#supports_anonymous_source)|上書き、`supports_anonymous_source`メソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることを示します。 (上書き[itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source))。|

詳細については、[非同期メッセージ ブロック](../asynchronous-message-blocks.md)を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`unbounded_buffer`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="accept_message"></a> accept_message

これによって提供されたメッセージを受け入れる`unbounded_buffer`メッセージング ブロック、呼び出し元に所有権を転送します。

```
virtual message<_Type> * accept_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

##  <a name="consume_message"></a> consume_message

によって以前に提供されたメッセージを使用して、`unbounded_buffer`メッセージング ブロックと、呼び出し元に所有権を譲渡する、ターゲットによって予約されています。

```
virtual message<_Type> * consume_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`使用しているオブジェクトします。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

### <a name="remarks"></a>Remarks

ような`accept`への呼び出しでは、前に必ずが`reserve`します。

##  <a name="dequeue"></a> デキュー

項目を削除、`unbounded_buffer`メッセージング ブロックします。

```
_Type dequeue();
```

### <a name="return-value"></a>戻り値

削除されたメッセージのペイロード、`unbounded_buffer`します。

##  <a name="enqueue"></a> エンキュー

項目を追加、`unbounded_buffer`メッセージング ブロックします。

```
bool enqueue(
   _Type const&                 _Item
);
```

### <a name="parameters"></a>パラメーター

*_Item*<br/>
追加する項目。

### <a name="return-value"></a>戻り値

**true**項目が受け入れられた場合**false**それ以外の場合。

##  <a name="link_target_notification"></a> link_target_notification

この新しいターゲットがリンクされていることを通知するコールバック`unbounded_buffer`メッセージング ブロックします。

```
virtual void link_target_notification(
   _Inout_ ITarget<_Type> *                 _PTarget
);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
新たにリンクされたターゲットへのポインター。

##  <a name="propagate_message"></a> propagate_message

メッセージを非同期的に渡す、`ISource`このブロック`unbounded_buffer`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status propagate_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>

  `message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md#message_status)メッセージとは、ターゲットの決定を示す値。

##  <a name="propagate_output_messages"></a> propagate_output_messages

場所、 `message` `_PMessage`この`unbounded_buffer`メッセージング ブロックと、すべてのリンクのターゲットに提供しようとします。

```
virtual void propagate_output_messages();
```

### <a name="remarks"></a>Remarks

別のメッセージが既に事前内にあるこのかどうか、 `unbounded_buffer`、リンクされたターゲットへの伝達は、前のメッセージを受け入れるか、使用するまでは行われません。 最初にターゲットの正常にリンクされた`accept`または`consume`、所有権のあるメッセージとその他のターゲットできますし、メッセージが表示ない、です。

##  <a name="process_input_messages"></a> process_input_messages

場所、 `message` `_PMessage`この`unbounded_buffer`メッセージング ブロックと、すべてのリンクのターゲットに提供しようとします。

```
virtual void process_input_messages(
   _Inout_ message<_Type> *                 _PMessage
);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
処理されるメッセージへのポインター。

##  <a name="release_message"></a> release_message

前のメッセージの予約を解放します。

```
virtual void release_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`リリースされているオブジェクトします。

##  <a name="reserve_message"></a> reserve_message

これによって以前に提供されたメッセージを予約`unbounded_buffer`メッセージング ブロックします。

```
virtual bool reserve_message(
   runtime_object_identity                 _MsgId
);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`予約されているオブジェクトします。

### <a name="return-value"></a>戻り値

**true**場合は、メッセージが正常に予約された、 **false**それ以外の場合。

### <a name="remarks"></a>Remarks

後`reserve`と呼ばれる場合は、返された場合**true**, か、`consume`または`release`かかるまたはメッセージの所有権を解放のいずれかを呼び出す必要があります。

##  <a name="resume_propagation"></a> resume_propagation

予約が解放された後は、伝達を再開します。

```
virtual void resume_propagation();
```

##  <a name="send_message"></a> send_message

メッセージを同期的に渡す、`ISource`このブロック`unbounded_buffer`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status send_message(
   _Inout_ message<_Type> *                 _PMessage,
   _Inout_ ISource<_Type> *                 _PSource
);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>

  `message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md#message_status)メッセージとは、ターゲットの決定を示す値。

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

上書き、`supports_anonymous_source`メソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることを示します。

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>戻り値

**true**ブロックは延期しないため、メッセージを提供します。

##  <a name="ctor"></a> unbounded_buffer

構築、`unbounded_buffer`メッセージング ブロックします。

```
unbounded_buffer();

unbounded_buffer(
   filter_method const&                 _Filter
);

unbounded_buffer(
   Scheduler&                 _PScheduler
);

unbounded_buffer(
   Scheduler&                 _PScheduler,
   filter_method const&                 _Filter
);

unbounded_buffer(
   ScheduleGroup&                 _PScheduleGroup
);

unbounded_buffer(
   ScheduleGroup&                 _PScheduleGroup,
   filter_method const&                 _Filter
);
```

### <a name="parameters"></a>パラメーター

*フィルター (_f)*<br/>
提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `unbounded_buffer` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `unbounded_buffer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>Remarks

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

型`filter_method`シグネチャを持つ、ファンクターは、`bool (_Type const &)`これによって呼び出される`unbounded_buffer`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。

##  <a name="dtor"></a> ~unbounded_buffer

破棄、`unbounded_buffer`メッセージング ブロックします。

```
~unbounded_buffer();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[overwrite_buffer クラス](overwrite-buffer-class.md)<br/>
[single_assignment クラス](single-assignment-class.md)
