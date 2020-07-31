---
title: multitype_join クラス
ms.date: 11/04/2016
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
ms.openlocfilehash: c648e77e404cf39eab281a93e03d8b427da375f8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87205861"
---
# <a name="multitype_join-class"></a>multitype_join クラス

`multitype_join` メッセージング ブロックは、複数のソースと単一のターゲットを持つメッセージング ブロックで、それぞれのソースから受け取った異なる種類のメッセージを 1 つに結合して、結合されたメッセージのタプルをターゲットに渡します。

## <a name="syntax"></a>構文

```cpp
template<
    typename T,
    join_type _Jtype = non_greedy
>
class multitype_join: public ISource<typename _Unwrap<T>::type>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`tuple`ブロックによって結合および伝達されたメッセージのペイロードの種類。

*_Jtype*<br/>
このブロックの種類は `join` 、またはのいずれかです。 `greedy``non_greedy`

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`type`|の型のエイリアス `T` 。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[multitype_join](#ctor)|オーバーロードされます。 `multitype_join` メッセージング ブロックを構築します。|
|[~ multitype_join デストラクター](#dtor)|`multitype_join`メッセージングブロックを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[受入](#accept)|このブロックによって提供されたメッセージを受け入れ `multitype_join` 、所有権を呼び出し元に転送します。|
|[acquire_ref](#acquire_ref)|このメッセージングブロックの参照カウントを取得して `multitype_join` 、削除されないようにします。|
|[可能性](#consume)|は、メッセージングブロックによって既に提供され、ターゲットによって正常に予約されているメッセージを使用して、 `multitype_join` 所有権を呼び出し元に譲渡します。|
|[link_target](#link_target)|ターゲットブロックをこの `multitype_join` メッセージングブロックにリンクします。|
|[解除](#release)|前回成功したメッセージの予約を解放します。|
|[release_ref](#release_ref)|このメッセージングブロックの参照カウントを解放 `multiple_join` します。|
|[省](#reserve)|このメッセージングブロックによって以前に提供されたメッセージを予約 `multitype_join` します。|
|[unlink_target](#unlink_target)|このメッセージングブロックからターゲットブロックをリンク解除 `multitype_join` します。|
|[unlink_targets](#unlink_targets)|このメッセージングブロックのすべてのターゲットのリンクを解除 `multitype_join` します。 ( [ISource:: unlink_targets](isource-class.md#unlink_targets)よりも優先されます)。|

## <a name="remarks"></a>解説

詳細については、「[非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

`multitype_join`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="accept"></a><a name="accept"></a>受入

このブロックによって提供されたメッセージを受け入れ `multitype_join` 、所有権を呼び出し元に転送します。

```cpp
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `accept` 。

### <a name="return-value"></a>戻り値

現在呼び出し元に所有権があることを示すメッセージへのポインター。

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

このメッセージングブロックの参照カウントを取得して `multitype_join` 、削除されないようにします。

```cpp
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出しているターゲットブロックへのポインター。

### <a name="remarks"></a>解説

このメソッドは `ITarget` 、メソッドの実行中にこのソースにリンクされるオブジェクトによって呼び出され `link_target` ます。

## <a name="consume"></a><a name="consume"></a>可能性

は、メッセージングブロックによって既に提供され、ターゲットによって正常に予約されているメッセージを使用して、 `multitype_join` 所有権を呼び出し元に譲渡します。

```cpp
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
予約された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `consume` 。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

### <a name="remarks"></a>解説

`consume`メソッドはと似ていますが、常にを呼び出した後に、 `accept` 返されたを呼び出す必要があり `reserve` **`true`** ます。

## <a name="link_target"></a><a name="link_target"></a>link_target

ターゲットブロックをこの `multitype_join` メッセージングブロックにリンクします。

```cpp
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
`ITarget`このメッセージングブロックにリンクするブロックへのポインター `multitype_join` 。

## <a name="multitype_join"></a><a name="ctor"></a>multitype_join

`multitype_join` メッセージング ブロックを構築します。

```cpp
explicit multitype_join(
    T _Tuple);

multitype_join(
    Scheduler& _PScheduler,
    T _Tuple);

multitype_join(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

multitype_join(
    multitype_join&& _Join);
```

### <a name="parameters"></a>パラメーター

*_Tuple*<br/>
この `tuple` メッセージング ブロックのソースの `multitype_join` です。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

*_Join*<br/>
コピー元の `multitype_join` メッセージング ブロックです。 元のオブジェクトが孤立しており、これが移動コンストラクターになることに注意してください。

### <a name="remarks"></a>解説

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

移動の構築はロックの状況では行われません。ということは、移動時に処理中の軽量タスクがないことを確認するのはユーザーの責任です。 そうしないと、例外または不整合な状態で、多数の競合が発生します。

## <a name="multitype_join"></a><a name="dtor"></a>~ multitype_join

`multitype_join`メッセージングブロックを破棄します。

```cpp
~multitype_join();
```

## <a name="release"></a><a name="release"></a>解除

前回成功したメッセージの予約を解放します。

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` `message` 解放されるオブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `release` 。

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

このメッセージングブロックの参照カウントを解放 `multiple_join` します。

```cpp
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出しているターゲットブロックへのポインター。

### <a name="remarks"></a>解説

このメソッドは、このソースからリンク解除されているオブジェクトによって呼び出され `ITarget` ます。 ソースブロックは、ターゲットブロック用に予約されているすべてのリソースを解放できます。

## <a name="reserve"></a><a name="reserve"></a>省

このメッセージングブロックによって以前に提供されたメッセージを予約 `multitype_join` します。

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` `message` 予約されているオブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `reserve` 。

### <a name="return-value"></a>戻り値

**`true`** メッセージが正常に予約された場合は **`false`** 。それ以外の場合は。 予約は、さまざまな理由で失敗する可能性があります。これには、メッセージが既に別のターゲットによって既に予約または受け入れられている場合、ソースが予約を拒否する場合などがあります。

### <a name="remarks"></a>解説

を呼び出した後、成功した場合は、 `reserve` `consume` メッセージを `release` 取得または取得するために、またはのいずれかを呼び出す必要があります。

## <a name="unlink_target"></a><a name="unlink_target"></a>unlink_target

このメッセージングブロックからターゲットブロックをリンク解除 `multitype_join` します。

```cpp
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
`ITarget`このメッセージングブロックのリンクを解除するブロックへのポインター `multitype_join` 。

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

このメッセージングブロックのすべてのターゲットのリンクを解除 `multitype_join` します。

```cpp
virtual void unlink_targets();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[choice クラス](choice-class.md)<br/>
[join クラス](join-class.md)
