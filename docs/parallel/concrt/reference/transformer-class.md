---
title: transformer クラス
ms.date: 11/04/2016
f1_keywords:
- transformer
- AGENTS/concurrency::transformer
- AGENTS/concurrency::transformer::transformer
- AGENTS/concurrency::transformer::accept_message
- AGENTS/concurrency::transformer::consume_message
- AGENTS/concurrency::transformer::link_target_notification
- AGENTS/concurrency::transformer::propagate_message
- AGENTS/concurrency::transformer::propagate_to_any_targets
- AGENTS/concurrency::transformer::release_message
- AGENTS/concurrency::transformer::reserve_message
- AGENTS/concurrency::transformer::resume_propagation
- AGENTS/concurrency::transformer::send_message
- AGENTS/concurrency::transformer::supports_anonymous_source
helpviewer_keywords:
- transformer class
ms.assetid: eea71925-7043-4a92-bfd4-dbc0ece5d081
ms.openlocfilehash: cc35a4e2de2b29bb6d437dfcbf48ef361fefdfa3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618284"
---
# <a name="transformer-class"></a>transformer クラス

`transformer` メッセージング ブロックは、単一のターゲットと複数のソースを持つ順序付けられた `propagator_block` であり、1 つの種類のメッセージを複数受け入れ、別の種類のメッセージを無制限に格納することができます。

## <a name="syntax"></a>構文

```
template<class _Input, class _Output>
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>,
    multi_link_registry<ISource<_Input>>>;
```

#### <a name="parameters"></a>パラメーター

*(_I)*<br/>
バッファーで受け取ったメッセージのペイロードの型。

*(_O)*<br/>
メッセージのペイロードの型が格納され、バッファーが反映されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[transformer](#ctor)|オーバーロードされます。 `transformer` メッセージング ブロックを構築します。|
|[~ transformer デストラクター](#dtor)|破棄、`transformer`メッセージング ブロックします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れる`transformer`メッセージング ブロック、呼び出し元に所有権を転送します。|
|[consume_message](#consume_message)|によって以前に提供されたメッセージを使用して、`transformer`と呼び出し元に所有権を譲渡する、ターゲットによって予約済み。|
|[link_target_notification](#link_target_notification)|この新しいターゲットがリンクされていることを通知するコールバック`transformer`メッセージング ブロックします。|
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`transformer`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。|
|[propagate_to_any_targets](#propagate_to_any_targets)|入力メッセージでトランスフォーマー関数を実行します。|
|[release_message](#release_message)|前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|
|[reserve_message](#reserve_message)|これによって以前に提供されたメッセージを予約`transformer`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|
|[resume_propagation](#resume_propagation)|予約が解放された後は、伝達を再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`このブロック`transformer`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。|
|[supports_anonymous_source](#supports_anonymous_source)|上書き、`supports_anonymous_source`メソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることを示します。 (上書き[itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source))。|

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`transformer`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="accept_message"></a> accept_message

これによって提供されたメッセージを受け入れる`transformer`メッセージング ブロック、呼び出し元に所有権を転送します。

```
virtual message<_Output>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

##  <a name="consume_message"></a> consume_message

によって以前に提供されたメッセージを使用して、`transformer`と呼び出し元に所有権を譲渡する、ターゲットによって予約済み。

```
virtual message<_Output>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`使用しているオブジェクトします。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

### <a name="remarks"></a>Remarks

ような`accept`への呼び出しでは、前に必ずが`reserve`します。

##  <a name="link_target_notification"></a> link_target_notification

この新しいターゲットがリンクされていることを通知するコールバック`transformer`メッセージング ブロックします。

```
virtual void link_target_notification(_Inout_ ITarget<_Output> *);
```

##  <a name="propagate_message"></a> propagate_message

メッセージを非同期的に渡す、`ISource`このブロック`transformer`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status propagate_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

入力メッセージでトランスフォーマー関数を実行します。

```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Output> *);
```

##  <a name="release_message"></a> release_message

前のメッセージの予約を解放します。

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`リリースされているオブジェクトします。

##  <a name="reserve_message"></a> reserve_message

これによって以前に提供されたメッセージを予約`transformer`メッセージング ブロックします。

```
virtual bool reserve_message(runtime_object_identity _MsgId);
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

メッセージを同期的に渡す、`ISource`このブロック`transformer`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status send_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

上書き、`supports_anonymous_source`メソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることを示します。

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>戻り値

**true**ブロックは延期しないため、メッセージを提供します。

##  <a name="ctor"></a> トランスフォーマー

`transformer` メッセージング ブロックを構築します。

```
transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    Scheduler& _PScheduler,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget = NULL);

transformer(
    ScheduleGroup& _PScheduleGroup,
    _Transform_method const& _Func,
    _Inout_opt_ ITarget<_Output>* _PTarget,
    filter_method const& _Filter);
```

### <a name="parameters"></a>パラメーター

*_Func*<br/>
許容されるメッセージごとに呼び出される関数。

*_PTarget*<br/>
トランスフォーマーとリンクするターゲット ブロックへのポインター。

*フィルター (_f)*<br/>
提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `transformer` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `transformer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>Remarks

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

型`_Transform_method`シグネチャを持つ、ファンクターは、`_Output (_Input const &)`これによって呼び出される`transformer`メッセージング ブロックはメッセージを処理します。

型`filter_method`シグネチャを持つ、ファンクターは、`bool (_Input const &)`これによって呼び出される`transformer`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。

##  <a name="dtor"></a> ~transformer

破棄、`transformer`メッセージング ブロックします。

```
~transformer();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[call クラス](call-class.md)
