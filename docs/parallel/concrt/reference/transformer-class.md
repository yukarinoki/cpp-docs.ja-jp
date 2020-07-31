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
ms.openlocfilehash: adc83ab2d8268460b3a35be44f5733c8b6fa1c43
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217897"
---
# <a name="transformer-class"></a>transformer クラス

`transformer` メッセージング ブロックは、単一のターゲットと複数のソースを持つ順序付けられた `propagator_block` であり、1 つの種類のメッセージを複数受け入れ、別の種類のメッセージを無制限に格納することができます。

## <a name="syntax"></a>構文

```cpp
template<class _Input, class _Output>
class transformer : public propagator_block<single_link_registry<ITarget<_Output>>,
    multi_link_registry<ISource<_Input>>>;
```

### <a name="parameters"></a>パラメーター

*_Input*<br/>
バッファーによって受け入れられるメッセージのペイロードの種類。

*_Output*<br/>
バッファーに格納され、バッファーによって伝達されるメッセージのペイロードの種類。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[変換](#ctor)|オーバーロードされます。 `transformer` メッセージング ブロックを構築します。|
|[~ トランスフォーマーデストラクター](#dtor)|`transformer`メッセージングブロックを破棄します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|このメッセージングブロックによって提供されたメッセージを受け入れ `transformer` 、所有権を呼び出し元に転送します。|
|[consume_message](#consume_message)|によって提供され、ターゲットによって予約されているメッセージを使用して、 `transformer` 所有権を呼び出し元に譲渡します。|
|[link_target_notification](#link_target_notification)|新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `transformer` 。|
|[propagate_message](#propagate_message)|`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `transformer` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[propagate_to_any_targets](#propagate_to_any_targets)|入力メッセージに対してトランスフォーマー関数を実行します。|
|[release_message](#release_message)|以前のメッセージ予約を解放します。 ( [Source_block:: release_message](source-block-class.md#release_message)をオーバーライドします。)|
|[reserve_message](#reserve_message)|このメッセージングブロックによって以前に提供されたメッセージを予約 `transformer` します。 ( [Source_block:: reserve_message](source-block-class.md#reserve_message)をオーバーライドします。)|
|[resume_propagation](#resume_propagation)|予約が解放された後、伝達を再開します。 ( [Source_block:: resume_propagation](source-block-class.md#resume_propagation)をオーバーライドします。)|
|[send_message](#send_message)|`ISource`ブロックからこのメッセージングブロックにメッセージを同期的に渡し `transformer` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[supports_anonymous_source](#supports_anonymous_source)|このブロックがリンクされて `supports_anonymous_source` いないソースによって提供されるメッセージを受け入れることができることを示すために、メソッドをオーバーライドします。 ( [ITarget:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)よりも優先されます)。|

## <a name="remarks"></a>解説

詳細については、「[非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`transformer`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

このメッセージングブロックによって提供されたメッセージを受け入れ `transformer` 、所有権を呼び出し元に転送します。

```cpp
virtual message<_Output>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

によって提供され、ターゲットによって予約されているメッセージを使用して、 `transformer` 所有権を呼び出し元に譲渡します。

```cpp
virtual message<_Output>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
使用 `runtime_object_identity` `message` されているオブジェクトの。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

### <a name="remarks"></a>解説

に似 `accept` ていますが、の前には常にが呼び出され `reserve` ます。

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `transformer` 。

```cpp
virtual void link_target_notification(_Inout_ ITarget<_Output> *);
```

## <a name="propagate_message"></a><a name="propagate_message"></a>propagate_message

`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `transformer` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した[message_status](concurrency-namespace-enums.md)を示します。

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

入力メッセージに対してトランスフォーマー関数を実行します。

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<_Output> *);
```

## <a name="release_message"></a><a name="release_message"></a>release_message

以前のメッセージ予約を解放します。

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` `message` 解放されるオブジェクトの。

## <a name="reserve_message"></a><a name="reserve_message"></a>reserve_message

このメッセージングブロックによって以前に提供されたメッセージを予約 `transformer` します。

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` `message` 予約されているオブジェクトの。

### <a name="return-value"></a>戻り値

**`true`** メッセージが正常に予約された場合は **`false`** 。それ以外の場合は。

### <a name="remarks"></a>解説

が呼び出された後、 `reserve` がを返す場合 **`true`** `consume` は、 `release` メッセージの所有権を取得または解放するためにまたはのいずれかを呼び出す必要があります。

## <a name="resume_propagation"></a><a name="resume_propagation"></a>resume_propagation

予約が解放された後、伝達を再開します。

```cpp
virtual void resume_propagation();
```

## <a name="send_message"></a><a name="send_message"></a>send_message

`ISource`ブロックからこのメッセージングブロックにメッセージを同期的に渡し `transformer` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

```cpp
virtual message_status send_message(
    _Inout_ message<_Input>* _PMessage,
    _Inout_ ISource<_Input>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した[message_status](concurrency-namespace-enums.md)を示します。

## <a name="supports_anonymous_source"></a><a name="supports_anonymous_source"></a>supports_anonymous_source

このブロックがリンクされて `supports_anonymous_source` いないソースによって提供されるメッセージを受け入れることができることを示すために、メソッドをオーバーライドします。

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>戻り値

**`true`** ブロックは提供されたメッセージを延期しないためです。

## <a name="transformer"></a><a name="ctor"></a>変換

`transformer` メッセージング ブロックを構築します。

```cpp
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
受け入れられた各メッセージに対して呼び出される関数。

*_PTarget*<br/>
トランスフォーマーとリンクするターゲットブロックへのポインター。

*_Filter*<br/>
提供されたメッセージを受け入れるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `transformer` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `transformer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>解説

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

この型 `_Transform_method` は、 `_Output (_Input const &)` `transformer` メッセージを処理するためにこのメッセージングブロックによって呼び出される、署名付きのファンクタです。

この型は、提供された `filter_method` `bool (_Input const &)` メッセージを `transformer` 受け入れるかどうかを判断するために、このメッセージングブロックによって呼び出される、シグネチャを持つファンクタです。

## <a name="transformer"></a><a name="dtor"></a>~ トランスフォーマー

`transformer`メッセージングブロックを破棄します。

```cpp
~transformer();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[call クラス](call-class.md)
