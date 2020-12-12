---
description: '詳細情報: overwrite_buffer クラス'
title: overwrite_buffer クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
ms.openlocfilehash: 20acc133a988c145546e680acb394f0cb69307f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271396"
---
# <a name="overwrite_buffer-class"></a>overwrite_buffer クラス

`overwrite_buffer` メッセージング ブロックは、一度に 1 つのメッセージを格納することができる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。 新しいメッセージが与えられると、それまで格納されていたメッセージは上書きされます。

## <a name="syntax"></a>構文

```cpp
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
バッファーによって格納および反映されるメッセージのペイロードの種類。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[overwrite_buffer](#ctor)|オーバーロードされます。 `overwrite_buffer`メッセージングブロックを構築します。|
|[~ overwrite_buffer デストラクター](#dtor)|`overwrite_buffer`メッセージングブロックを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[has_value](#has_value)|この `overwrite_buffer` メッセージングブロックの値がまだあるかどうかを確認します。|
|[value](#value)|メッセージングブロックに格納されているメッセージの現在のペイロードへの参照を取得し `overwrite_buffer` ます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|このメッセージングブロックによって提供されたメッセージを受け入れ `overwrite_buffer` 、呼び出し元にメッセージのコピーを返します。|
|[consume_message](#consume_message)|は、メッセージングブロックによって既に提供され、ターゲットによって予約されているメッセージを使用して、 `overwrite_buffer` メッセージのコピーを呼び出し元に返します。|
|[link_target_notification](#link_target_notification)|新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `overwrite_buffer` 。|
|[propagate_message](#propagate_message)|`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `overwrite_buffer` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[propagate_to_any_targets](#propagate_to_any_targets)|を `message _PMessage` このメッセージングブロックに配置し、リンクされた `overwrite_buffer` すべてのターゲットに提供します。|
|[release_message](#release_message)|以前のメッセージ予約を解放します。 ( [Source_block:: release_message](source-block-class.md#release_message)をオーバーライドします。)|
|[reserve_message](#reserve_message)|このメッセージングブロックによって以前に提供されたメッセージを予約 `overwrite_buffer` します。 ( [Source_block:: reserve_message](source-block-class.md#reserve_message)をオーバーライドします。)|
|[resume_propagation](#resume_propagation)|予約が解放された後、伝達を再開します。 ( [Source_block:: resume_propagation](source-block-class.md#resume_propagation)をオーバーライドします。)|
|[send_message](#send_message)|`ISource`ブロックからこのメッセージングブロックにメッセージを同期的に渡し `overwrite_buffer` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[supports_anonymous_source](#supports_anonymous_source)|このブロックがリンクされて `supports_anonymous_source` いないソースによって提供されるメッセージを受け入れることができることを示すために、メソッドをオーバーライドします。 ( [ITarget:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)よりも優先されます)。|

## <a name="remarks"></a>解説

`overwrite_buffer`メッセージングブロックは、格納されているメッセージのコピーをそれぞれのターゲットに伝達します。

詳細については、「 [非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`overwrite_buffer`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="accept_message"></a><a name="accept_message"></a> accept_message

このメッセージングブロックによって提供されたメッセージを受け入れ `overwrite_buffer` 、呼び出し元にメッセージのコピーを返します。

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

### <a name="remarks"></a>解説

メッセージングブロックは、現在保持されて `overwrite_buffer` いるメッセージの所有権を譲渡するのではなく、メッセージのコピーをターゲットに返します。

## <a name="consume_message"></a><a name="consume_message"></a> consume_message

は、メッセージングブロックによって既に提供され、ターゲットによって予約されているメッセージを使用して、 `overwrite_buffer` メッセージのコピーを呼び出し元に返します。

```cpp
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
使用 `runtime_object_identity` `message` されているオブジェクトの。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

### <a name="remarks"></a>解説

に似 `accept` ていますが、の前には常にが呼び出され `reserve` ます。

## <a name="has_value"></a><a name="has_value"></a> has_value

この `overwrite_buffer` メッセージングブロックの値がまだあるかどうかを確認します。

```cpp
bool has_value() const;
```

### <a name="return-value"></a>戻り値

**`true`** ブロックが値を受け取った場合は **`false`** 。それ以外の場合は。

## <a name="link_target_notification"></a><a name="link_target_notification"></a> link_target_notification

新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `overwrite_buffer` 。

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
新しくリンクされたターゲットへのポインター。

## <a name="overwrite_buffer"></a><a name="dtor"></a> ~ overwrite_buffer

`overwrite_buffer`メッセージングブロックを破棄します。

```cpp
~overwrite_buffer();
```

## <a name="overwrite_buffer"></a><a name="ctor"></a> overwrite_buffer

`overwrite_buffer`メッセージングブロックを構築します。

```cpp
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

*_Filter*<br/>
提供されたメッセージを受け入れるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `overwrite_buffer` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `overwrite_buffer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>解説

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

この型は、提供された `filter_method` `bool (T const &)` メッセージを `overwrite_buffer` 受け入れるかどうかを判断するために、このメッセージングブロックによって呼び出される、シグネチャを持つファンクタです。

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `overwrite_buffer` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

```cpp
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した [message_status](concurrency-namespace-enums.md) を示します。

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a> propagate_to_any_targets

を `message _PMessage` このメッセージングブロックに配置し、リンクされた `overwrite_buffer` すべてのターゲットに提供します。

```cpp
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message`この `overwrite_buffer` が所有権を取得したオブジェクトへのポインター。

### <a name="remarks"></a>解説

このメソッドは、 `overwrite_buffer` 新しく受け入れられたメッセージを使用して、の現在のメッセージを上書きし `_PMessage` ます。

## <a name="send_message"></a><a name="send_message"></a> send_message

`ISource`ブロックからこのメッセージングブロックにメッセージを同期的に渡し `overwrite_buffer` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

```cpp
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した [message_status](concurrency-namespace-enums.md) を示します。

## <a name="supports_anonymous_source"></a><a name="supports_anonymous_source"></a> supports_anonymous_source

このブロックがリンクされて `supports_anonymous_source` いないソースによって提供されるメッセージを受け入れることができることを示すために、メソッドをオーバーライドします。

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>戻り値

**`true`** ブロックは提供されたメッセージを延期しないためです。

## <a name="release_message"></a><a name="release_message"></a> release_message

以前のメッセージ予約を解放します。

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` `message` 解放されるオブジェクトの。

## <a name="reserve_message"></a><a name="reserve_message"></a> reserve_message

このメッセージングブロックによって以前に提供されたメッセージを予約 `overwrite_buffer` します。

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

## <a name="resume_propagation"></a><a name="resume_propagation"></a> resume_propagation

予約が解放された後、伝達を再開します。

```cpp
virtual void resume_propagation();
```

## <a name="value"></a><a name="value"></a> 値

メッセージングブロックに格納されているメッセージの現在のペイロードへの参照を取得し `overwrite_buffer` ます。

```cpp
T value();
```

### <a name="return-value"></a>戻り値

現在格納されているメッセージのペイロード。

### <a name="remarks"></a>解説

このメソッドから制御が戻った直後に、に格納されている値が変更される `overwrite_buffer` 可能性があります。 このメソッドは、にメッセージが現在格納されていない場合、メッセージが到着するまで待機 `overwrite_buffer` します。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[unbounded_buffer クラス](unbounded-buffer-class.md)<br/>
[single_assignment クラス](single-assignment-class.md)
