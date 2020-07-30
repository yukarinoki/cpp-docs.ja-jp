---
title: join クラス
ms.date: 11/04/2016
f1_keywords:
- join
- AGENTS/concurrency::join
- AGENTS/concurrency::join::join
- AGENTS/concurrency::join::accept_message
- AGENTS/concurrency::join::consume_message
- AGENTS/concurrency::join::link_target_notification
- AGENTS/concurrency::join::propagate_message
- AGENTS/concurrency::join::propagate_to_any_targets
- AGENTS/concurrency::join::release_message
- AGENTS/concurrency::join::reserve_message
- AGENTS/concurrency::join::resume_propagation
helpviewer_keywords:
- join class
ms.assetid: d2217119-70a1-40b6-809f-c1c13a571c3f
ms.openlocfilehash: c65eed8abafe424fa27c5b9a72d3c73b7127b68e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219587"
---
# <a name="join-class"></a>join クラス

`join` メッセージング ブロックは、単一のターゲットと複数のソースを持つ順序付けられた `propagator_block` であり、各ソースから、種類が `T` であるメッセージを結合します。

## <a name="syntax"></a>構文

```cpp
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
ブロックによって結合および伝達されたメッセージのペイロードの種類。

*_Jtype*<br/>
このブロックの種類は `join` 、またはのいずれかです。 `greedy``non_greedy`

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[join](#ctor)|オーバーロードされます。 `join` メッセージング ブロックを構築します。|
|[~ 結合デストラクター](#dtor)|ブロックを破棄 `join` します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|このメッセージングブロックによって提供されたメッセージを受け入れ `join` 、所有権を呼び出し元に転送します。|
|[consume_message](#consume_message)|メッセージングブロックによって既に提供され、ターゲットによって予約されているメッセージを使用して、 `join` 所有権を呼び出し元に譲渡します。|
|[link_target_notification](#link_target_notification)|新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `join` 。|
|[propagate_message](#propagate_message)|`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `join` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[propagate_to_any_targets](#propagate_to_any_targets)|すべての送信元からの入力メッセージを含む出力メッセージを構築します。 この出力メッセージを各ターゲットに送信します。|
|[release_message](#release_message)|以前のメッセージ予約を解放します。 ( [Source_block:: release_message](source-block-class.md#release_message)をオーバーライドします。)|
|[reserve_message](#reserve_message)|このメッセージングブロックによって以前に提供されたメッセージを予約 `join` します。 ( [Source_block:: reserve_message](source-block-class.md#reserve_message)をオーバーライドします。)|
|[resume_propagation](#resume_propagation)|予約が解放された後、伝達を再開します。 ( [Source_block:: resume_propagation](source-block-class.md#resume_propagation)をオーバーライドします。)|

## <a name="remarks"></a>解説

詳細については、「[非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`join`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

このメッセージングブロックによって提供されたメッセージを受け入れ `join` 、所有権を呼び出し元に転送します。

```cpp
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

メッセージングブロックによって既に提供され、ターゲットによって予約されているメッセージを使用して、 `join` 所有権を呼び出し元に譲渡します。

```cpp
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
使用 `runtime_object_identity` `message` されているオブジェクトの。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

### <a name="remarks"></a>解説

に似 `accept` ていますが、の前には常にが呼び出され `reserve` ます。

## <a name="join"></a><a name="ctor"></a>結合

`join` メッセージング ブロックを構築します。

```cpp
join(
    size_t _NumInputs);

join(
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs);

join(
    Scheduler& _PScheduler,
    size_t _NumInputs,
    filter_method const& _Filter);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs);

join(
    ScheduleGroup& _PScheduleGroup,
    size_t _NumInputs,
    filter_method const& _Filter);
```

### <a name="parameters"></a>パラメーター

*_NumInputs*<br/>
この `join` ブロックが許可される入力の数。

*_Filter*<br/>
提供されたメッセージを受け入れるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `join` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>解説

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

この型は、提供された `filter_method` `bool (T const &)` メッセージを `join` 受け入れるかどうかを判断するために、このメッセージングブロックによって呼び出される、シグネチャを持つファンクタです。

## <a name="join"></a><a name="dtor"></a>~ join

ブロックを破棄 `join` します。

```cpp
~join();
```

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `join` 。

```cpp
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```

## <a name="propagate_message"></a><a name="propagate_message"></a>propagate_message

`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `join` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

```cpp
message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した[message_status](concurrency-namespace-enums.md)を示します。

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

すべての送信元からの入力メッセージを含む出力メッセージを構築します。 この出力メッセージを各ターゲットに送信します。

```cpp
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
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

このメッセージングブロックによって以前に提供されたメッセージを予約 `join` します。

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

### <a name="return-value"></a>戻り値

**`true`** メッセージが正常に予約された場合は **`false`** 。それ以外の場合は。

### <a name="remarks"></a>解説

が呼び出された後、 `reserve` がを返す場合 **`true`** `consume` は、 `release` メッセージの所有権を取得または解放するためにまたはのいずれかを呼び出す必要があります。

## <a name="resume_propagation"></a><a name="resume_propagation"></a>resume_propagation

予約が解放された後、伝達を再開します。

```cpp
virtual void resume_propagation();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[choice クラス](choice-class.md)<br/>
[multitype_join クラス](multitype-join-class.md)
