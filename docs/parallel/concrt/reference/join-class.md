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
ms.openlocfilehash: d04ef90750c609d77fc8bf963bb996a90444f079
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343875"
---
# <a name="join-class"></a>join クラス

`join` メッセージング ブロックは、単一のターゲットと複数のソースを持つ順序付けられた `propagator_block` であり、各ソースから、種類が `T` であるメッセージを結合します。

## <a name="syntax"></a>構文

```
template<class T,
    join_type _Jtype = non_greedy>
class join : public propagator_block<single_link_registry<ITarget<std::vector<T>>>,
    multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
メッセージのペイロードの種類は、参加しているし、ブロックによって反映されます。

*_Jtype*<br/>
種類の`join`ブロックか、これは`greedy`または `non_greedy`

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[join](#ctor)|オーバーロードされます。 `join` メッセージング ブロックを構築します。|
|[~ join デストラクター](#dtor)|破棄、`join`ブロックします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れる`join`メッセージング ブロック、呼び出し元に所有権を転送します。|
|[consume_message](#consume_message)|によって以前に提供されたメッセージを使用して、`join`メッセージング ブロックと、呼び出し元に所有権を譲渡する、ターゲットによって予約されています。|
|[link_target_notification](#link_target_notification)|この新しいターゲットがリンクされていることを通知するコールバック`join`メッセージング ブロックします。|
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`join`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。|
|[propagate_to_any_targets](#propagate_to_any_targets)|これらがすべて反映メッセージと、各ソースから入力メッセージを含む、出力メッセージを構築します。 各ターゲットにこの出力メッセージを送信します。|
|[release_message](#release_message)|前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|
|[reserve_message](#reserve_message)|これによって以前に提供されたメッセージを予約`join`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|
|[resume_propagation](#resume_propagation)|予約が解放された後は、伝達を再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`join`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="accept_message"></a> accept_message

これによって提供されたメッセージを受け入れる`join`メッセージング ブロック、呼び出し元に所有権を転送します。

```
virtual message<_OutputType>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

##  <a name="consume_message"></a> consume_message

によって以前に提供されたメッセージを使用して、`join`メッセージング ブロックと、呼び出し元に所有権を譲渡する、ターゲットによって予約されています。

```
virtual message<_OutputType>* consume_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`使用しているオブジェクトします。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

### <a name="remarks"></a>Remarks

ような`accept`への呼び出しでは、前に必ずが`reserve`します。

##  <a name="ctor"></a> 結合

`join` メッセージング ブロックを構築します。

```
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
この数が入力`join`ブロックが許可されます。

*フィルター (_f)*<br/>
提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `join` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>Remarks

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

型`filter_method`シグネチャを持つ、ファンクターは、`bool (T const &)`これによって呼び出される`join`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。

##  <a name="dtor"></a> ~join

破棄、`join`ブロックします。

```
~join();
```

##  <a name="link_target_notification"></a> link_target_notification

この新しいターゲットがリンクされていることを通知するコールバック`join`メッセージング ブロックします。

```
virtual void link_target_notification(_Inout_ ITarget<std::vector<T>> *);
```

##  <a name="propagate_message"></a> propagate_message

メッセージを非同期的に渡す、`ISource`このブロック`join`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。

```
message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets

これらがすべて反映メッセージと、各ソースから入力メッセージを含む、出力メッセージを構築します。 各ターゲットにこの出力メッセージを送信します。

```
void propagate_to_any_targets(_Inout_opt_ message<_OutputType> *);
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

これによって以前に提供されたメッセージを予約`join`メッセージング ブロックします。

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

### <a name="return-value"></a>戻り値

**true**場合は、メッセージが正常に予約された、 **false**それ以外の場合。

### <a name="remarks"></a>Remarks

後`reserve`と呼ばれる場合は、返された場合**true**, か、`consume`または`release`かかるまたはメッセージの所有権を解放のいずれかを呼び出す必要があります。

##  <a name="resume_propagation"></a> resume_propagation

予約が解放された後は、伝達を再開します。

```
virtual void resume_propagation();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[choice クラス](choice-class.md)<br/>
[multitype_join クラス](multitype-join-class.md)
