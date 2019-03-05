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
ms.openlocfilehash: e36441f53c9b53c9826ee92b2892142a522d7243
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298153"
---
# <a name="timer-class"></a>timer クラス

`timer` メッセージング ブロックは単一のターゲットを持つ `source_block` であり、指定された時間の経過後か、特定の間隔で、メッセージをターゲットに送信することができます。

## <a name="syntax"></a>構文

```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
このブロックの出力メッセージのペイロードの型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[timer](#ctor)|オーバーロードされます。 構築、`timer`メッセージング ブロックを指定した間隔の特定のメッセージを起動します。|
|[~ timer デストラクター](#dtor)|破棄、`timer`メッセージング ブロックします。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[pause](#pause)|停止、`timer`メッセージング ブロックします。 繰り返し場合`timer`ブロックのメッセージングを再起動するとそれ以降`start()`を呼び出します。 – 非繰り返しタイマーの場合、これと同じ効果として、`stop`呼び出します。|
|[start](#start)|開始、`timer`メッセージング ブロックします。 これまでのミリ秒数の指定が呼び出されると、指定した値が反映されるとダウン ストリーム、`message`します。|
|[stop](#stop)|停止、`timer`メッセージング ブロックします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れる`timer`メッセージング ブロック、呼び出し元に所有権を転送します。|
|[consume_message](#consume_message)|によって以前に提供されたメッセージを使用して、`timer`と呼び出し元に所有権を譲渡する、ターゲットによって予約済み。|
|[link_target_notification](#link_target_notification)|この新しいターゲットがリンクされていることを通知するコールバック`timer`メッセージング ブロックします。|
|[propagate_to_any_targets](#propagate_to_any_targets)|によって生成されたメッセージを提供しようとする、`timer`にすべてのリンクのターゲット ブロック。|
|[release_message](#release_message)|前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|
|[reserve_message](#reserve_message)|これによって以前に提供されたメッセージを予約`timer`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|
|[resume_propagation](#resume_propagation)|予約が解放された後は、伝達を再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[source_block](source-block-class.md)

`timer`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="accept_message"></a> accept_message

これによって提供されたメッセージを受け入れる`timer`メッセージング ブロック、呼び出し元に所有権を転送します。

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

##  <a name="consume_message"></a> consume_message

によって以前に提供されたメッセージを使用して、`timer`と呼び出し元に所有権を譲渡する、ターゲットによって予約済み。

```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`使用しているオブジェクトします。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

### <a name="remarks"></a>Remarks

ような`accept`への呼び出しでは、前に必ずが`reserve`します。

##  <a name="link_target_notification"></a> link_target_notification

この新しいターゲットがリンクされていることを通知するコールバック`timer`メッセージング ブロックします。

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
新たにリンクされたターゲットへのポインター。

##  <a name="pause"></a> 一時停止

停止、`timer`メッセージング ブロックします。 繰り返し場合`timer`ブロックのメッセージングを再起動するとそれ以降`start()`を呼び出します。 – 非繰り返しタイマーの場合、これと同じ効果として、`stop`呼び出します。

```
void pause();
```

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

によって生成されたメッセージを提供しようとする、`timer`にすべてのリンクのターゲット ブロック。

```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
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

これによって以前に提供されたメッセージを予約`timer`メッセージング ブロックします。

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

##  <a name="start"></a> 開始

開始、`timer`メッセージング ブロックします。 これまでのミリ秒数の指定が呼び出されると、指定した値が反映されるとダウン ストリーム、`message`します。

```
void start();
```

##  <a name="stop"></a> 停止

停止、`timer`メッセージング ブロックします。

```
void stop();
```

##  <a name="ctor"></a> タイマー

構築、`timer`メッセージング ブロックを指定した間隔の特定のメッセージを起動します。

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

*_Ms*<br/>
指定したメッセージに反映されるダウン ストリームの開始呼び出しの後までの経過時間 (ミリ秒) の数。

*value*<br/>
タイマーが経過するとは、ダウン ストリーム伝達される値。

*_PTarget*<br/>
タイマーがメッセージを伝達するターゲット。

*_Repeating*<br/>
True の場合は、タイマーを定期的に起動を示します。 すべて`_Ms`(ミリ秒)。

*_Scheduler*<br/>
`Scheduler`オブジェクト用の伝達のタスクを`timer`メッセージング ブロックがスケジュールされているがスケジュールされています。

*_ScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `timer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>Remarks

`_Scheduler` または `_ScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

##  <a name="dtor"></a> ~ タイマー

破棄、`timer`メッセージング ブロックします。

```
~timer();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
