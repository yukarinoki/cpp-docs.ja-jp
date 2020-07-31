---
title: timer クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
ms.openlocfilehash: 026aef03bb813585decb206c1691835330a4dd05
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224943"
---
# <a name="timer-class"></a>timer クラス

`timer` メッセージング ブロックは単一のターゲットを持つ `source_block` であり、指定された時間の経過後か、特定の間隔で、メッセージをターゲットに送信することができます。

## <a name="syntax"></a>構文

```cpp
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
このブロックの出力メッセージのペイロードの種類。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[期限](#ctor)|オーバーロードされます。 `timer`指定された期間の後に特定のメッセージを起動するメッセージングブロックを構築します。|
|[~ timer デストラクター](#dtor)|`timer`メッセージングブロックを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[pause](#pause)|`timer`メッセージングブロックを停止します。 反復的なメッセージングブロックの場合は `timer` 、後続の呼び出しで再起動でき `start()` ます。 非繰り返しタイマーの場合、呼び出しと同じ効果があり `stop` ます。|
|[start](#start)|`timer`メッセージングブロックを開始します。 このが呼び出されてから指定されたミリ秒数が経過すると、指定された値はとして下流に反映され `message` ます。|
|[stop](#stop)|`timer`メッセージングブロックを停止します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|[説明]|
|----------|-----------------|
|[accept_message](#accept_message)|このメッセージングブロックによって提供されたメッセージを受け入れ `timer` 、所有権を呼び出し元に転送します。|
|[consume_message](#consume_message)|によって提供され、ターゲットによって予約されているメッセージを使用して、 `timer` 所有権を呼び出し元に譲渡します。|
|[link_target_notification](#link_target_notification)|新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `timer` 。|
|[propagate_to_any_targets](#propagate_to_any_targets)|ブロックによって生成されたメッセージを、リンクされたすべてのターゲットに提供しようとし `timer` ます。|
|[release_message](#release_message)|以前のメッセージ予約を解放します。 ( [Source_block:: release_message](source-block-class.md#release_message)をオーバーライドします。)|
|[reserve_message](#reserve_message)|このメッセージングブロックによって以前に提供されたメッセージを予約 `timer` します。 ( [Source_block:: reserve_message](source-block-class.md#reserve_message)をオーバーライドします。)|
|[resume_propagation](#resume_propagation)|予約が解放された後、伝達を再開します。 ( [Source_block:: resume_propagation](source-block-class.md#resume_propagation)をオーバーライドします。)|

## <a name="remarks"></a>解説

詳細については、「[非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[source_block](source-block-class.md)

`timer`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

このメッセージングブロックによって提供されたメッセージを受け入れ `timer` 、所有権を呼び出し元に転送します。

```cpp
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

によって提供され、ターゲットによって予約されているメッセージを使用して、 `timer` 所有権を呼び出し元に譲渡します。

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

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

新しいターゲットがこのメッセージングブロックにリンクされていることを通知するコールバック `timer` 。

```cpp
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
新しくリンクされたターゲットへのポインター。

## <a name="pause"></a><a name="pause"></a>停止

`timer`メッセージングブロックを停止します。 反復的なメッセージングブロックの場合は `timer` 、後続の呼び出しで再起動でき `start()` ます。 非繰り返しタイマーの場合、呼び出しと同じ効果があり `stop` ます。

```cpp
void pause();
```

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

ブロックによって生成されたメッセージを、リンクされたすべてのターゲットに提供しようとし `timer` ます。

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
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

このメッセージングブロックによって以前に提供されたメッセージを予約 `timer` します。

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

## <a name="start"></a><a name="start"></a>着手

`timer`メッセージングブロックを開始します。 このが呼び出されてから指定されたミリ秒数が経過すると、指定された値はとして下流に反映され `message` ます。

```cpp
void start();
```

## <a name="stop"></a><a name="stop"></a>停止

`timer`メッセージングブロックを停止します。

```cpp
void stop();
```

## <a name="timer"></a><a name="ctor"></a>期限

`timer`指定された期間の後に特定のメッセージを起動するメッセージングブロックを構築します。

```cpp
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

*_Ms*<br/>
指定したメッセージが下流に伝達されるまでの呼び出しが開始されてからの経過時間 (ミリ秒単位)。

*value*<br/>
タイマーが経過したときにダウンストリームに反映される値。

*_PTarget*<br/>
タイマーがメッセージを伝達するターゲット。

*_Repeating*<br/>
True の場合は、タイマーがミリ秒ごとに定期的に起動されることを示し `_Ms` ます。

*_Scheduler*<br/>
`Scheduler`メッセージングブロックの反映タスクがスケジュールされているオブジェクト `timer` 。

*_ScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `timer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>解説

`_Scheduler` または `_ScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

## <a name="timer"></a><a name="dtor"></a>~ timer

`timer`メッセージングブロックを破棄します。

```cpp
~timer();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
