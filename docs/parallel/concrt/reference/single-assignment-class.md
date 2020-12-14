---
description: '詳細情報: single_assignment クラス'
title: single_assignment クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
ms.openlocfilehash: d01426843f2e9fe1106f7cb68c103c392cdf1ebd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188658"
---
# <a name="single_assignment-class"></a>single_assignment クラス

`single_assignment` メッセージング ブロックは、一度だけ書き込むことができる `propagator_block` を 1 つ格納できる、複数のターゲットと複数のソースを持つ順序付けられた `message` です。

## <a name="syntax"></a>構文

```cpp
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
バッファーによって格納および反映されたメッセージのペイロードの種類。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[single_assignment](#ctor)|オーバーロードされます。 `single_assignment` メッセージング ブロックを構築します。|
|[~ single_assignment デストラクター](#dtor)|`single_assignment`メッセージングブロックを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[has_value](#has_value)|この `single_assignment` メッセージングブロックが値を使用して初期化されているかどうかを確認します。|
|[value](#value)|メッセージングブロックに格納されているメッセージの現在のペイロードへの参照を取得し `single_assignment` ます。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|このメッセージングブロックによって提供されたメッセージを受け入れ `single_assignment` 、呼び出し元にメッセージのコピーを返します。|
|[consume_message](#consume_message)|によって提供され、ターゲットによって予約されているメッセージを使用して、 `single_assignment` メッセージのコピーを呼び出し元に返します。|
|[link_target_notification](#link_target_notification)|新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `single_assignment` 。|
|[propagate_message](#propagate_message)|`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `single_assignment` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[propagate_to_any_targets](#propagate_to_any_targets)|を `message _PMessage` このメッセージングブロックに配置し、リンクされた `single_assignment` すべてのターゲットに提供します。|
|[release_message](#release_message)|以前のメッセージ予約を解放します。 ( [Source_block:: release_message](source-block-class.md#release_message)をオーバーライドします。)|
|[reserve_message](#reserve_message)|このメッセージングブロックによって以前に提供されたメッセージを予約 `single_assignment` します。 ( [Source_block:: reserve_message](source-block-class.md#reserve_message)をオーバーライドします。)|
|[resume_propagation](#resume_propagation)|予約が解放された後、伝達を再開します。 ( [Source_block:: resume_propagation](source-block-class.md#resume_propagation)をオーバーライドします。)|
|[send_message](#send_message)|`ISource`ブロックからこのメッセージングブロックにメッセージを同期的に渡し `single_assignment` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|

## <a name="remarks"></a>解説

`single_assignment`メッセージングブロックは、メッセージのコピーを各ターゲットに伝達します。

詳細については、「 [非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`single_assignment`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="accept_message"></a><a name="accept_message"></a> accept_message

このメッセージングブロックによって提供されたメッセージを受け入れ `single_assignment` 、呼び出し元にメッセージのコピーを返します。

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

### <a name="remarks"></a>解説

メッセージングブロックは、現在保持されて `single_assignment` いるメッセージの所有権を譲渡するのではなく、メッセージのコピーをターゲットに返します。

## <a name="consume_message"></a><a name="consume_message"></a> consume_message

によって提供され、ターゲットによって予約されているメッセージを使用して、 `single_assignment` メッセージのコピーを呼び出し元に返します。

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

この `single_assignment` メッセージングブロックが値を使用して初期化されているかどうかを確認します。

```cpp
bool has_value() const;
```

### <a name="return-value"></a>戻り値

**`true`** ブロックが値を受け取った場合は **`false`** 。それ以外の場合は。

## <a name="link_target_notification"></a><a name="link_target_notification"></a> link_target_notification

新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `single_assignment` 。

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
新しくリンクされたターゲットへのポインター。

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `single_assignment` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

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

を `message` `_PMessage` このメッセージングブロックに配置し、リンクされた `single_assignment` すべてのターゲットに提供します。

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message`この `single_assignment` メッセージングブロックが所有権を取得したへのポインター。

## <a name="release_message"></a><a name="release_message"></a> release_message

以前のメッセージ予約を解放します。

```cpp
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` `message` 解放されるオブジェクトの。

## <a name="reserve_message"></a><a name="reserve_message"></a> reserve_message

このメッセージングブロックによって以前に提供されたメッセージを予約 `single_assignment` します。

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

## <a name="send_message"></a><a name="send_message"></a> send_message

`ISource`ブロックからこのメッセージングブロックにメッセージを同期的に渡し `single_assignment` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

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

## <a name="single_assignment"></a><a name="ctor"></a> single_assignment

`single_assignment` メッセージング ブロックを構築します。

```cpp
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

*_Filter*<br/>
提供されたメッセージを受け入れるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `single_assignment` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `single_assignment` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>解説

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

この型は、提供された `filter_method` `bool (T const &)` メッセージを `single_assignment` 受け入れるかどうかを判断するために、このメッセージングブロックによって呼び出される、シグネチャを持つファンクタです。

## <a name="single_assignment"></a><a name="dtor"></a> ~ single_assignment

`single_assignment`メッセージングブロックを破棄します。

```cpp
~single_assignment();
```

## <a name="value"></a><a name="value"></a> 値

メッセージングブロックに格納されているメッセージの現在のペイロードへの参照を取得し `single_assignment` ます。

```cpp
T const& value();
```

### <a name="return-value"></a>戻り値

格納されているメッセージのペイロード。

### <a name="remarks"></a>解説

このメソッドは、メッセージングブロックにメッセージが現在格納されていない場合、メッセージが到着するまで待機 `single_assignment` します。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[overwrite_buffer クラス](overwrite-buffer-class.md)<br/>
[unbounded_buffer クラス](unbounded-buffer-class.md)
