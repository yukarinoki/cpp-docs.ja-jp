---
title: overwrite_buffer クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 622f439355c9d8b059ac48f0bdc1f57c1b32e5eb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387667"
---
# <a name="overwritebuffer-class"></a>overwrite_buffer クラス

`overwrite_buffer` メッセージング ブロックは、一度に 1 つのメッセージを格納することができる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。 新しいメッセージが与えられると、それまで格納されていたメッセージは上書きされます。

## <a name="syntax"></a>構文

```
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
メッセージのペイロードの型が格納され、バッファーによって反映されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[overwrite_buffer](#ctor)|オーバーロードされます。 構築、`overwrite_buffer`メッセージング ブロックします。|
|[~ overwrite_buffer デストラクター](#dtor)|破棄、`overwrite_buffer`メッセージング ブロックします。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[has_value](#has_value)|チェックするかどうかこの`overwrite_buffer`メッセージング ブロックはまだ値。|
|[value](#value)|格納されているメッセージの現在のペイロードへの参照を取得、`overwrite_buffer`メッセージング ブロックします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[accept_message](#accept_message)|これによって提供されたメッセージを受け入れる`overwrite_buffer`メッセージング ブロック、呼び出し元に、メッセージのコピーを返します。|
|[consume_message](#consume_message)|によって以前に提供されたメッセージを使用して、`overwrite_buffer`メッセージング ブロックとメッセージのコピーを返す、呼び出し元に、ターゲットによって予約されています。|
|[link_target_notification](#link_target_notification)|この新しいターゲットがリンクされていることを通知するコールバック`overwrite_buffer`メッセージング ブロックします。|
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`overwrite_buffer`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。|
|[propagate_to_any_targets](#propagate_to_any_targets)|場所、`message _PMessage`この`overwrite_buffer`メッセージング ブロックと、すべてのリンクのターゲットに提供しています。|
|[release_message](#release_message)|前のメッセージの予約を解放します。 (上書き[source_block::release_message](source-block-class.md#release_message))。|
|[reserve_message](#reserve_message)|これによって以前に提供されたメッセージを予約`overwrite_buffer`メッセージング ブロックします。 (上書き[source_block::reserve_message](source-block-class.md#reserve_message))。|
|[resume_propagation](#resume_propagation)|予約が解放された後は、伝達を再開します。 (上書き[source_block::resume_propagation](source-block-class.md#resume_propagation))。|
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`このブロック`overwrite_buffer`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。|
|[supports_anonymous_source](#supports_anonymous_source)|上書き、`supports_anonymous_source`メソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることを示します。 (上書き[itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source))。|

## <a name="remarks"></a>Remarks

`overwrite_buffer`メッセージング ブロックが各ターゲットが格納されているメッセージのコピーを伝達します。

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

[propagator_block](propagator-block-class.md)

`overwrite_buffer`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="accept_message"></a> accept_message

これによって提供されたメッセージを受け入れる`overwrite_buffer`メッセージング ブロック、呼び出し元に、メッセージのコピーを返します。

```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

### <a name="remarks"></a>Remarks

`overwrite_buffer`現在保持されているメッセージの所有権を譲渡するのではなく、メッセージング、そのターゲットにメッセージのコピーがブロックを返します。

##  <a name="consume_message"></a> consume_message

によって以前に提供されたメッセージを使用して、`overwrite_buffer`メッセージング ブロックとメッセージのコピーを返す、呼び出し元に、ターゲットによって予約されています。

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

チェックするかどうかこの`overwrite_buffer`メッセージング ブロックはまだ値。

```
bool has_value() const;
```

### <a name="return-value"></a>戻り値

`true` ブロックは、値を受け取った場合`false`それ以外の場合。

##  <a name="link_target_notification"></a> link_target_notification

この新しいターゲットがリンクされていることを通知するコールバック`overwrite_buffer`メッセージング ブロックします。

```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
新たにリンクされたターゲットへのポインター。

##  <a name="dtor"></a> ~overwrite_buffer

破棄、`overwrite_buffer`メッセージング ブロックします。

```
~overwrite_buffer();
```

##  <a name="ctor"></a> overwrite_buffer

構築、`overwrite_buffer`メッセージング ブロックします。

```
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

*フィルター (_f)*<br/>
提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `overwrite_buffer` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `overwrite_buffer` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>Remarks

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

型`filter_method`シグネチャを持つ、ファンクターは、`bool (T const &)`これによって呼び出される`overwrite_buffer`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。

##  <a name="propagate_message"></a> propagate_message

メッセージを非同期的に渡す、`ISource`このブロック`overwrite_buffer`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。

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

場所、`message _PMessage`この`overwrite_buffer`メッセージング ブロックと、すべてのリンクのターゲットに提供しています。

```
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
ポインターを`message`オブジェクトこの`overwrite_buffer`がの所有権を取得します。

### <a name="remarks"></a>Remarks

このメソッドは、現在のメッセージを上書き、`overwrite_buffer`新しく受け入れたメッセージ`_PMessage`します。

##  <a name="send_message"></a> send_message

メッセージを同期的に渡す、`ISource`このブロック`overwrite_buffer`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。

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

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

上書き、`supports_anonymous_source`メソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることを示します。

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>戻り値

`true` ブロックは延期しないため、メッセージを提供します。

##  <a name="release_message"></a> release_message

前のメッセージの予約を解放します。

```
virtual void release_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`リリースされているオブジェクトします。

##  <a name="reserve_message"></a> reserve_message

これによって以前に提供されたメッセージを予約`overwrite_buffer`メッセージング ブロックします。

```
virtual bool reserve_message(runtime_object_identity _MsgId);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`予約されているオブジェクトします。

### <a name="return-value"></a>戻り値

`true` 場合は、メッセージが正常に予約された、`false`それ以外の場合。

### <a name="remarks"></a>Remarks

後`reserve`と呼ばれる場合は、返された場合`true`, か、`consume`または`release`かかるまたはメッセージの所有権を解放のいずれかを呼び出す必要があります。

##  <a name="resume_propagation"></a> resume_propagation

予約が解放された後は、伝達を再開します。

```
virtual void resume_propagation();
```

##  <a name="value"></a> 値

格納されているメッセージの現在のペイロードへの参照を取得、`overwrite_buffer`メッセージング ブロックします。

```
T value();
```

### <a name="return-value"></a>戻り値

現在格納されているメッセージのペイロード。

### <a name="remarks"></a>Remarks

格納された値、`overwrite_buffer`このメソッドを返した直後後に変更できます。 このメソッドは、メッセージが現在格納されていない場合、メッセージが到着するまでに待機、`overwrite_buffer`します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[unbounded_buffer クラス](unbounded-buffer-class.md)<br/>
[single_assignment クラス](single-assignment-class.md)
