---
title: choice クラス
ms.date: 11/04/2016
f1_keywords:
- choice
- AGENTS/concurrency::choice
- AGENTS/concurrency::choice::choice
- AGENTS/concurrency::choice::accept
- AGENTS/concurrency::choice::acquire_ref
- AGENTS/concurrency::choice::consume
- AGENTS/concurrency::choice::has_value
- AGENTS/concurrency::choice::index
- AGENTS/concurrency::choice::link_target
- AGENTS/concurrency::choice::release
- AGENTS/concurrency::choice::release_ref
- AGENTS/concurrency::choice::reserve
- AGENTS/concurrency::choice::unlink_target
- AGENTS/concurrency::choice::unlink_targets
- AGENTS/concurrency::choice::value
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
ms.openlocfilehash: a5b9bc26b6d9ec66dc74e7adaad31eea1eece118
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224982"
---
# <a name="choice-class"></a>choice クラス

`choice` メッセージング ブロックは、複数のソースと単一のターゲットを持つブロックであり、一連のソースとの制御フローの相互作用を表します。 choice ブロックは、複数のソースのいずれかがメッセージを生成するのを待ち、そのメッセージを生成したソースのインデックスを伝達します。

## <a name="syntax"></a>構文

```cpp
template<
    class T
>
class choice: public ISource<size_t>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
`tuple`入力ソースのペイロードを表す、ベースの型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|[説明]|
|----------|-----------------|
|`type`|の型のエイリアス `T` 。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|[説明]|
|----------|-----------------|
|[choice](#ctor)|オーバーロードされます。 `choice` メッセージング ブロックを構築します。|
|[~ choice デストラクター](#dtor)|`choice`メッセージングブロックを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|[説明]|
|----------|-----------------|
|[受入](#accept)|このブロックによって提供されたメッセージを受け入れ `choice` 、所有権を呼び出し元に転送します。|
|[acquire_ref](#acquire_ref)|このメッセージングブロックの参照カウントを取得して `choice` 、削除されないようにします。|
|[可能性](#consume)|このメッセージングブロックによって既に提供され、ターゲットによって正常に予約されているメッセージを使用して、 `choice` 所有権を呼び出し元に譲渡します。|
|[has_value](#has_value)|この `choice` メッセージングブロックが値を使用して初期化されているかどうかを確認します。|
|[インデックス](#index)|`tuple`メッセージングブロックによって選択された要素を表すへのインデックスを返し `choice` ます。|
|[link_target](#link_target)|ターゲットブロックをこの `choice` メッセージングブロックにリンクします。|
|[解除](#release)|前回成功したメッセージの予約を解放します。|
|[release_ref](#release_ref)|このメッセージングブロックの参照カウントを解放 `choice` します。|
|[省](#reserve)|このメッセージングブロックによって以前に提供されたメッセージを予約 `choice` します。|
|[unlink_target](#unlink_target)|このメッセージングブロックからターゲットブロックをリンク解除 `choice` します。|
|[unlink_targets](#unlink_targets)|このメッセージングブロックのすべてのターゲットのリンクを解除 `choice` します。 ( [ISource:: unlink_targets](isource-class.md#unlink_targets)よりも優先されます)。|
|[value](#value)|メッセージングブロックによってインデックスが選択されたメッセージを取得し `choice` ます。|

## <a name="remarks"></a>解説

Choice ブロックは、受信メッセージの1つのみが使用されることを保証します。

詳細については、「[非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

`choice`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="accept"></a><a name="accept"></a>受入

このブロックによって提供されたメッセージを受け入れ `choice` 、所有権を呼び出し元に転送します。

```cpp
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `accept` 。

### <a name="return-value"></a>戻り値

現在呼び出し元に所有権があることを示すメッセージへのポインター。

## <a name="acquire_ref"></a><a name="acquire_ref"></a>acquire_ref

このメッセージングブロックの参照カウントを取得して `choice` 、削除されないようにします。

```cpp
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出しているターゲットブロックへのポインター。

### <a name="remarks"></a>解説

このメソッドは `ITarget` 、メソッドの実行中にこのソースにリンクされるオブジェクトによって呼び出され `link_target` ます。

## <a name="choice"></a><a name="ctor"></a>どれ

`choice` メッセージング ブロックを構築します。

```cpp
explicit choice(
    T _Tuple);

choice(
    Scheduler& _PScheduler,
    T _Tuple);

choice(
    ScheduleGroup& _PScheduleGroup,
    T _Tuple);

choice(
    choice&& _Choice);
```

### <a name="parameters"></a>パラメーター

*_Tuple*<br/>
選択肢のソースの `tuple` です。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

*_Choice*<br/>
コピー元の `choice` メッセージング ブロックです。 元のオブジェクトが孤立しており、これが移動コンストラクターになることに注意してください。

### <a name="remarks"></a>解説

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

移動の構築はロックの状況では行われません。ということは、移動時に処理中の軽量タスクがないことを確認するのはユーザーの責任です。 そうしないと、例外または不整合な状態で、多数の競合が発生します。

## <a name="choice"></a><a name="dtor"></a>~ choice

`choice`メッセージングブロックを破棄します。

```cpp
~choice();
```

## <a name="consume"></a><a name="consume"></a>可能性

このメッセージングブロックによって既に提供され、ターゲットによって正常に予約されているメッセージを使用して、 `choice` 所有権を呼び出し元に譲渡します。

```cpp
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
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

## <a name="has_value"></a><a name="has_value"></a>has_value

この `choice` メッセージングブロックが値を使用して初期化されているかどうかを確認します。

```cpp
bool has_value() const;
```

### <a name="return-value"></a>戻り値

**`true`** ブロックが値を受け取った場合は **`false`** 。それ以外の場合は。

## <a name="index"></a><a name="index"></a>化

`tuple`メッセージングブロックによって選択された要素を表すへのインデックスを返し `choice` ます。

```cpp
size_t index();
```

### <a name="return-value"></a>戻り値

メッセージインデックス。

### <a name="remarks"></a>解説

メッセージペイロードは、メソッドを使用して抽出でき `get` ます。

## <a name="link_target"></a><a name="link_target"></a>link_target

ターゲットブロックをこの `choice` メッセージングブロックにリンクします。

```cpp
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
`ITarget`このメッセージングブロックにリンクするブロックへのポインター `choice` 。

## <a name="release"></a><a name="release"></a>解除

前回成功したメッセージの予約を解放します。

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` `message` 解放されるオブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `release` 。

## <a name="release_ref"></a><a name="release_ref"></a>release_ref

このメッセージングブロックの参照カウントを解放 `choice` します。

```cpp
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出しているターゲットブロックへのポインター。

### <a name="remarks"></a>解説

このメソッドは、このソースからリンク解除されているオブジェクトによって呼び出され `ITarget` ます。 ソースブロックは、ターゲットブロック用に予約されているすべてのリソースを解放できます。

## <a name="reserve"></a><a name="reserve"></a>省

このメッセージングブロックによって以前に提供されたメッセージを予約 `choice` します。

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
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

このメッセージングブロックからターゲットブロックをリンク解除 `choice` します。

```cpp
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
`ITarget`このメッセージングブロックのリンクを解除するブロックへのポインター `choice` 。

## <a name="unlink_targets"></a><a name="unlink_targets"></a>unlink_targets

このメッセージングブロックのすべてのターゲットのリンクを解除 `choice` します。

```cpp
virtual void unlink_targets();
```

### <a name="remarks"></a>解説

内部ブロックのデストラクター `single_assignment` が適切にリンク解除されるため、このメソッドをデストラクターから呼び出す必要はありません。

## <a name="value"></a><a name="value"></a> の値

メッセージングブロックによってインデックスが選択されたメッセージを取得し `choice` ます。

```cpp
template <
    typename _Payload_type
>
_Payload_type const& value();
```

### <a name="parameters"></a>パラメーター

*_Payload_type*<br/>
メッセージペイロードの種類。

### <a name="return-value"></a>戻り値

メッセージのペイロード。

### <a name="remarks"></a>解説

`choice`メッセージングブロックは、さまざまなペイロードの種類を持つ入力を受け取ることができるため、取得の時点でペイロードの種類を指定する必要があります。 メソッドの結果に基づいて型を特定でき `index` ます。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[join クラス](join-class.md)<br/>
[single_assignment クラス](single-assignment-class.md)
