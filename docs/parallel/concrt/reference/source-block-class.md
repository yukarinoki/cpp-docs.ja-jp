---
title: source_block クラス
ms.date: 11/04/2016
f1_keywords:
- source_block
- AGENTS/concurrency::source_block
- AGENTS/concurrency::source_block::source_block
- AGENTS/concurrency::source_block::accept
- AGENTS/concurrency::source_block::acquire_ref
- AGENTS/concurrency::source_block::consume
- AGENTS/concurrency::source_block::link_target
- AGENTS/concurrency::source_block::release
- AGENTS/concurrency::source_block::release_ref
- AGENTS/concurrency::source_block::reserve
- AGENTS/concurrency::source_block::unlink_target
- AGENTS/concurrency::source_block::unlink_targets
- AGENTS/concurrency::source_block::accept_message
- AGENTS/concurrency::source_block::async_send
- AGENTS/concurrency::source_block::consume_message
- AGENTS/concurrency::source_block::enable_batched_processing
- AGENTS/concurrency::source_block::initialize_source
- AGENTS/concurrency::source_block::link_target_notification
- AGENTS/concurrency::source_block::process_input_messages
- AGENTS/concurrency::source_block::propagate_output_messages
- AGENTS/concurrency::source_block::propagate_to_any_targets
- AGENTS/concurrency::source_block::release_message
- AGENTS/concurrency::source_block::remove_targets
- AGENTS/concurrency::source_block::reserve_message
- AGENTS/concurrency::source_block::resume_propagation
- AGENTS/concurrency::source_block::sync_send
- AGENTS/concurrency::source_block::unlink_target_notification
- AGENTS/concurrency::source_block::wait_for_outstanding_async_sends
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
ms.openlocfilehash: 304bc65d969fa677d67bf578021a63f628e0a1f5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228441"
---
# <a name="source_block-class"></a>source_block クラス

`source_block` クラスは、ソースのみのブロックの抽象基底クラスです。 このクラスには、基本的なリンク管理機能および一般的なエラー チェック機能が用意されています。

## <a name="syntax"></a>構文

```cpp
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```

### <a name="parameters"></a>パラメーター

*_TargetLinkRegistry*<br/>
ターゲットリンクを保持するために使用されるリンクレジストリ。

*_MessageProcessorType*<br/>
メッセージ処理のプロセッサの種類。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|[説明]|
|----------|-----------------|
|`target_iterator`|接続されたターゲットをウォークする反復子。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[source_block](#ctor)|`source_block` オブジェクトを構築します。|
|[~ source_block デストラクター](#dtor)|`source_block` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[受入](#accept)|このオブジェクトによって提供されたメッセージを受け取り `source_block` 、所有権を呼び出し元に転送します。|
|[acquire_ref](#acquire_ref)|`source_block`削除を防止するために、このオブジェクトの参照カウントを取得します。|
|[可能性](#consume)|このオブジェクトによって既に提供され、ターゲットによって正常に予約されているメッセージを使用して、 `source_block` 所有権を呼び出し元に譲渡します。|
|[link_target](#link_target)|ターゲットブロックをこのオブジェクトにリンク `source_block` します。|
|[解除](#release)|前回成功したメッセージの予約を解放します。|
|[release_ref](#release_ref)|このオブジェクトの参照カウントを解放 `source_block` します。|
|[省](#reserve)|このオブジェクトによって以前に提供されたメッセージを予約 `source_block` します。|
|[unlink_target](#unlink_target)|このオブジェクトからターゲットブロックのリンクを解除 `source_block` します。|
|[unlink_targets](#unlink_targets)|このオブジェクトからすべてのターゲットブロックのリンクを解除 `source_block` します。 ( [ISource:: unlink_targets](isource-class.md#unlink_targets)よりも優先されます)。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|[説明]|
|----------|-----------------|
|[accept_message](#accept_message)|派生クラスでオーバーライドされると、ソースによって提供されるメッセージを受け入れます。 メッセージブロックは、このメソッドをオーバーライドしてを検証し、メッセージを返す必要があり `_MsgId` ます。|
|[async_send](#async_send)|メッセージを非同期にキューに入れ、伝達タスクを開始します (まだ完了していない場合)。|
|[consume_message](#consume_message)|派生クラスでオーバーライドされると、以前に予約されていたメッセージを使用します。|
|[enable_batched_processing](#enable_batched_processing)|このブロックのバッチ処理を有効にします。|
|[initialize_source](#initialize_source)|この内でを初期化し `message_propagator` `source_block` ます。|
|[link_target_notification](#link_target_notification)|新しいターゲットがこのオブジェクトにリンクされていることを通知するコールバック `source_block` 。|
|[process_input_messages](#process_input_messages)|入力メッセージを処理します。 これは、から派生した伝達子ブロックにのみ有効です source_block|
|[propagate_output_messages](#propagate_output_messages)|メッセージをターゲットに伝達します。|
|[propagate_to_any_targets](#propagate_to_any_targets)|派生クラスでオーバーライドされると、指定したメッセージをリンクされたターゲットのいずれかまたはすべてに伝達します。 これは、メッセージブロックの主要な反映ルーチンです。|
|[release_message](#release_message)|派生クラスでオーバーライドされると、以前のメッセージ予約を解放します。|
|[remove_targets](#remove_targets)|このソースブロックのターゲットリンクをすべて削除します。 これは、デストラクターから呼び出す必要があります。|
|[reserve_message](#reserve_message)|派生クラスでオーバーライドされると、このオブジェクトによって以前に提供されたメッセージを予約し `source_block` ます。|
|[resume_propagation](#resume_propagation)|派生クラスでオーバーライドされると、予約が解放された後に伝達を再開します。|
|[sync_send](#sync_send)|既に実行されていない場合は、メッセージを同期的にキューに入れ、伝達タスクを開始します。|
|[unlink_target_notification](#unlink_target_notification)|ターゲットがこのオブジェクトからリンク解除されたことを通知するコールバック `source_block` 。|
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|すべての非同期伝達が完了するまで待機します。 この伝達子に固有のスピン待機は、すべての非同期伝達がブロックを破棄する前に完了するまでの時間を確保するために、メッセージブロックのデストラクターで使用されます。|

## <a name="remarks"></a>解説

このクラスによって提供されるリンク管理と同期を利用するには、メッセージブロックをこのブロックから派生させる必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

`source_block`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="accept"></a><a name="accept"></a>受入

このオブジェクトによって提供されたメッセージを受け取り `source_block` 、所有権を呼び出し元に転送します。

```cpp
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `accept` 。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

### <a name="remarks"></a>解説

パラメーターがの場合、メソッドは[invalid_argument](../../../standard-library/invalid-argument-class.md)例外をスローし `_PTarget` `NULL` ます。

メソッドは、 `accept` このブロックによってメッセージが提供されている間、ターゲットによって呼び出され `ISource` ます。 `propagate` `ITarget` このソースがメッセージのコピーを作成することにした場合、返されるメッセージポインターは、ブロックのメソッドに渡されたものと異なる場合があります。

## <a name="accept_message"></a><a name="accept_message"></a>accept_message

派生クラスでオーバーライドされると、ソースによって提供されるメッセージを受け入れます。 メッセージブロックは、このメソッドをオーバーライドしてを検証し、メッセージを返す必要があり `_MsgId` ます。

```cpp
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
オブジェクトのランタイムオブジェクト id `message` 。

### <a name="return-value"></a>戻り値

現在呼び出し元に所有権があることを示すメッセージへのポインター。

### <a name="remarks"></a>解説

所有権を譲渡するには、元のメッセージポインターが返される必要があります。 所有権を維持するには、メッセージペイロードのコピーを作成して返す必要があります。

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

`source_block`削除を防止するために、このオブジェクトの参照カウントを取得します。

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```

### <a name="remarks"></a>解説

このメソッドは `ITarget` 、メソッドの実行中にこのソースにリンクされるオブジェクトによって呼び出され `link_target` ます。

## <a name="async_send"></a><a name="async_send"></a>async_send

メッセージを非同期にキューに入れ、伝達タスクを開始します (まだ完了していない場合)。

```cpp
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>パラメーター

*_Msg*<br/>
`message`非同期に送信するオブジェクトへのポインター。

## <a name="consume"></a><a name="consume"></a>可能性

このオブジェクトによって既に提供され、ターゲットによって正常に予約されているメッセージを使用して、 `source_block` 所有権を呼び出し元に譲渡します。

```cpp
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
予約された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `consume` 。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

### <a name="remarks"></a>解説

パラメーターがの場合、メソッドは[invalid_argument](../../../standard-library/invalid-argument-class.md)例外をスローし `_PTarget` `NULL` ます。

パラメーターがを[bad_target](bad-target-class.md) `_PTarget` 呼び出したターゲットを表していない場合、メソッドは bad_target 例外をスローし `reserve` ます。

`consume`メソッドはと似ていますが、常にを呼び出した後に、 `accept` 返されたを呼び出す必要があり `reserve` **`true`** ます。

## <a name="consume_message"></a><a name="consume_message"></a>consume_message

派生クラスでオーバーライドされると、以前に予約されていたメッセージを使用します。

```cpp
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
使用 `runtime_object_identity` `message` されているオブジェクトの。

### <a name="return-value"></a>戻り値

現在呼び出し元に所有権があることを示すメッセージへのポインター。

### <a name="remarks"></a>解説

に似 `accept` ていますが、の前には常にが呼び出され `reserve` ます。

## <a name="enable_batched_processing"></a><a name="enable_batched_processing"></a>enable_batched_processing

このブロックのバッチ処理を有効にします。

```cpp
void enable_batched_processing();
```

## <a name="initialize_source"></a><a name="initialize_source"></a>initialize_source

この内でを初期化し `message_propagator` `source_block` ます。

```cpp
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>パラメーター

*_PScheduler*<br/>
タスクをスケジュールするために使用するスケジューラ。

*_PScheduleGroup*<br/>
タスクをスケジュールするために使用されるスケジュールグループ。

## <a name="link_target"></a><a name="link_target"></a>link_target

ターゲットブロックをこのオブジェクトにリンク `source_block` します。

```cpp
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
`ITarget`このオブジェクトにリンクするブロックへのポインター `source_block` 。

### <a name="remarks"></a>解説

パラメーターがの場合、メソッドは[invalid_argument](../../../standard-library/invalid-argument-class.md)例外をスローし `_PTarget` `NULL` ます。

## <a name="link_target_notification"></a><a name="link_target_notification"></a>link_target_notification

新しいターゲットがこのオブジェクトにリンクされていることを通知するコールバック `source_block` 。

```cpp
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```

## <a name="process_input_messages"></a><a name="process_input_messages"></a>process_input_messages

入力メッセージを処理します。 これは、から派生した伝達子ブロックにのみ有効です source_block

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
処理するメッセージへのポインター。

## <a name="propagate_output_messages"></a><a name="propagate_output_messages"></a>propagate_output_messages

メッセージをターゲットに伝達します。

```cpp
virtual void propagate_output_messages();
```

## <a name="propagate_to_any_targets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets

派生クラスでオーバーライドされると、指定したメッセージをリンクされたターゲットのいずれかまたはすべてに伝達します。 これは、メッセージブロックの主要な反映ルーチンです。

```cpp
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
伝達されるメッセージへのポインター。

## <a name="release"></a><a name="release"></a>解除

前回成功したメッセージの予約を解放します。

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
予約された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `release` 。

### <a name="remarks"></a>解説

パラメーターがの場合、メソッドは[invalid_argument](../../../standard-library/invalid-argument-class.md)例外をスローし `_PTarget` `NULL` ます。

パラメーターがを[bad_target](bad-target-class.md) `_PTarget` 呼び出したターゲットを表していない場合、メソッドは bad_target 例外をスローし `reserve` ます。

## <a name="release_message"></a><a name="release_message"></a>release_message

派生クラスでオーバーライドされると、以前のメッセージ予約を解放します。

```cpp
virtual void release_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` `message` 解放されるオブジェクトの。

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

このオブジェクトの参照カウントを解放 `source_block` します。

```cpp
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出しているターゲットブロックへのポインター。

### <a name="remarks"></a>解説

このメソッドは、このソースからリンク解除されているオブジェクトによって呼び出され `ITarget` ます。 ソースブロックは、ターゲットブロック用に予約されているすべてのリソースを解放できます。

## <a name="remove_targets"></a><a name="remove_targets"></a>remove_targets

このソースブロックのターゲットリンクをすべて削除します。 これは、デストラクターから呼び出す必要があります。

```cpp
void remove_targets();
```

## <a name="reserve"></a><a name="reserve"></a>省

このオブジェクトによって以前に提供されたメッセージを予約 `source_block` します。

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `reserve` 。

### <a name="return-value"></a>戻り値

**`true`** メッセージが正常に予約された場合は **`false`** 。それ以外の場合は。 予約は、さまざまな理由で失敗する可能性があります。これには、メッセージが既に別のターゲットによって既に予約または受け入れられている場合、ソースが予約を拒否する場合などがあります。

### <a name="remarks"></a>解説

パラメーターがの場合、メソッドは[invalid_argument](../../../standard-library/invalid-argument-class.md)例外をスローし `_PTarget` `NULL` ます。

を呼び出した後、成功した場合は、 `reserve` `consume` メッセージを `release` 取得または取得するために、またはのいずれかを呼び出す必要があります。

## <a name="reserve_message"></a><a name="reserve_message"></a>reserve_message

派生クラスでオーバーライドされると、このオブジェクトによって以前に提供されたメッセージを予約し `source_block` ます。

```cpp
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` `message` 予約されているオブジェクトの。

### <a name="return-value"></a>戻り値

**`true`** メッセージが正常に予約された場合は **`false`** 。それ以外の場合は。

### <a name="remarks"></a>解説

が呼び出された後、 `reserve` がを返す場合 **`true`** `consume` は、 `release` メッセージの所有権を取得または解放するためにまたはのいずれかを呼び出す必要があります。

## <a name="resume_propagation"></a><a name="resume_propagation"></a>resume_propagation

派生クラスでオーバーライドされると、予約が解放された後に伝達を再開します。

```cpp
virtual void resume_propagation() = 0;
```

## <a name="source_block"></a><a name="ctor"></a>source_block

`source_block` オブジェクトを構築します。

```cpp
source_block();
```

## <a name="source_block"></a><a name="dtor"></a>~ source_block

`source_block` オブジェクトを破棄します。

```cpp
virtual ~source_block();
```

## <a name="sync_send"></a><a name="sync_send"></a>sync_send

既に実行されていない場合は、メッセージを同期的にキューに入れ、伝達タスクを開始します。

```cpp
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```

### <a name="parameters"></a>パラメーター

*_Msg*<br/>
`message`同期的に送信するオブジェクトへのポインター。

## <a name="unlink_target"></a><a name="unlink_target"></a>unlink_target

このオブジェクトからターゲットブロックのリンクを解除 `source_block` します。

```cpp
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
`ITarget`このオブジェクトからリンクを解除するブロックへのポインター `source_block` 。

### <a name="remarks"></a>解説

パラメーターがの場合、メソッドは[invalid_argument](../../../standard-library/invalid-argument-class.md)例外をスローし `_PTarget` `NULL` ます。

## <a name="unlink_target_notification"></a><a name="unlink_target_notification"></a>unlink_target_notification

ターゲットがこのオブジェクトからリンク解除されたことを通知するコールバック `source_block` 。

```cpp
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
`ITarget`リンク解除されたブロック。

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

このオブジェクトからすべてのターゲットブロックのリンクを解除 `source_block` します。

```cpp
virtual void unlink_targets();
```

## <a name="wait_for_outstanding_async_sends"></a><a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends

すべての非同期伝達が完了するまで待機します。 この伝達子に固有のスピン待機は、すべての非同期伝達がブロックを破棄する前に完了するまでの時間を確保するために、メッセージブロックのデストラクターで使用されます。

```cpp
void wait_for_outstanding_async_sends();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[ISource クラス](isource-class.md)
