---
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
ms.openlocfilehash: 5a27fb6cdc13fbbd3ceb8a85adacf5491ddc3ce1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593480"
---
# <a name="singleassignment-class"></a>single_assignment クラス

`single_assignment` メッセージング ブロックは、一度だけ書き込むことができる `propagator_block` を 1 つ格納できる、複数のターゲットと複数のソースを持つ順序付けられた `message` です。

## <a name="syntax"></a>構文

```
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
メッセージのペイロードの型が格納され、バッファーによって反映されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[single_assignment](#ctor)|オーバーロードされます。 `single_assignment` メッセージング ブロックを構築します。|
|[~ single_assignment デストラクター](#dtor)|破棄、`single_assignment`メッセージング ブロックします。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[has_value](#has_value)|チェックするかどうかこれ`single_assignment`メッセージング ブロックを値はまだ初期化されています。|
|[値](#value)|格納されているメッセージの現在のペイロードへの参照を取得、`single_assignment`メッセージング ブロックします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れる`single_assignment`メッセージング ブロック、呼び出し元に、メッセージのコピーを返します。|
|[consume_message](#consume_message)|によって以前に提供されたメッセージを使用して、`single_assignment`とメッセージのコピーを返す、呼び出し元に、ターゲットによって予約済み。|
|[link_target_notification](#link_target_notification)|この新しいターゲットがリンクされていることを通知するコールバック`single_assignment`メッセージング ブロックします。|
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`single_assignment`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。|
|[propagate_to_any_targets](#propagate_to_any_targets)|場所、`message _PMessage`この`single_assignment`メッセージング ブロックと、すべてのリンクのターゲットに提供しています。|
|[release_message](#release_message)|前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|
|[reserve_message](#reserve_message)|これによって以前に提供されたメッセージを予約`single_assignment`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|
|[resume_propagation](#resume_propagation)|予約が解放された後は、伝達を再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`このブロック`single_assignment`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。|

## <a name="remarks"></a>Remarks

A`single_assignment`メッセージング ブロックがターゲットごとにそのメッセージのコピーを伝達します。

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`single_assignment`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="accept_message"></a> accept_message

これによって提供されたメッセージを受け入れる`single_assignment`メッセージング ブロック、呼び出し元に、メッセージのコピーを返します。

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

### <a name="remarks"></a>Remarks

`single_assignment`現在保持されているメッセージの所有権を譲渡するのではなく、メッセージング、そのターゲットにメッセージのコピーがブロックを返します。

##  <a name="consume_message"></a> consume_message

によって以前に提供されたメッセージを使用して、`single_assignment`とメッセージのコピーを返す、呼び出し元に、ターゲットによって予約済み。

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

##  <a name="has_value"></a> has_value

チェックするかどうかこれ`single_assignment`メッセージング ブロックを値はまだ初期化されています。

```
bool has_value() const;
```

### <a name="return-value"></a>戻り値

**true**ブロックは、値を受け取った場合**false**それ以外の場合。

##  <a name="link_target_notification"></a> link_target_notification

この新しいターゲットがリンクされていることを通知するコールバック`single_assignment`メッセージング ブロックします。

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
新たにリンクされたターゲットへのポインター。

##  <a name="propagate_message"></a> propagate_message

メッセージを非同期的に渡す、`ISource`このブロック`single_assignment`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status propagate_message(
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

場所、 `message` `_PMessage`この`single_assignment`メッセージング ブロックと、すべてのリンクのターゲットに提供しています。

```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
ポインターを`message`この`single_assignment`メッセージング ブロックがの所有権を取得します。

##  <a name="release_message"></a> release_message

前のメッセージの予約を解放します。

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`リリースされているオブジェクトします。

##  <a name="reserve_message"></a> reserve_message

これによって以前に提供されたメッセージを予約`single_assignment`メッセージング ブロックします。

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

メッセージを同期的に渡す、`ISource`このブロック`single_assignment`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status send_message(
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

##  <a name="ctor"></a> single_assignment

`single_assignment` メッセージング ブロックを構築します。

```
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

*フィルター (_f)*<br/>
提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `single_assignment` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `single_assignment` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>Remarks

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

型`filter_method`シグネチャを持つ、ファンクターは、`bool (T const &)`これによって呼び出される`single_assignment`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。

##  <a name="dtor"></a> ~single_assignment

破棄、`single_assignment`メッセージング ブロックします。

```
~single_assignment();
```

##  <a name="value"></a> 値

格納されているメッセージの現在のペイロードへの参照を取得、`single_assignment`メッセージング ブロックします。

```
T const& value();
```

### <a name="return-value"></a>戻り値

格納されたメッセージのペイロード。

### <a name="remarks"></a>Remarks

このメソッドは、メッセージが現在格納されていない場合、メッセージが到着するまでに待機、`single_assignment`メッセージング ブロックします。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[overwrite_buffer クラス](overwrite-buffer-class.md)<br/>
[unbounded_buffer クラス](unbounded-buffer-class.md)

