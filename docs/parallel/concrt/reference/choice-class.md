---
title: choice クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 039f69f31c5a92cf07f96442c30bd59b0cc6f40e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414577"
---
# <a name="choice-class"></a>choice クラス

`choice` メッセージング ブロックは、複数のソースと単一のターゲットを持つブロックであり、一連のソースとの制御フローの相互作用を表します。 choice ブロックは、複数のソースのいずれかがメッセージを生成するのを待ち、そのメッセージを生成したソースのインデックスを伝達します。

## <a name="syntax"></a>構文

```
template<
    class T
>
class choice: public ISource<size_t>;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
A `tuple`-ベースの入力ソースのペイロードを表す型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`type`|型の別名の`T`します。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[選択しました。](#ctor)|オーバーロードされます。 `choice` メッセージング ブロックを構築します。|
|[~ choice デストラクター](#dtor)|破棄、`choice`メッセージング ブロックします。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[accept](#accept)|これによって提供されたメッセージを受け入れる`choice`ブロック、呼び出し元に所有権を転送します。|
|[acquire_ref](#acquire_ref)|この参照カウントを取得`choice`メッセージング ブロックは、削除されないようにします。|
|[使用します。](#consume)|これによって以前に提供されたメッセージを使用して`choice`メッセージング ブロックと、呼び出し元に所有権を譲渡する、ターゲットが正常に予約されています。|
|[has_value](#has_value)|チェックするかどうかこれ`choice`メッセージング ブロックを値はまだ初期化されています。|
|[index](#index)|インデックスを返します、`tuple`によって選択された要素を表す、`choice`メッセージング ブロックします。|
|[link_target](#link_target)|このターゲット ブロックにリンク`choice`メッセージング ブロックします。|
|[release](#release)|以前に成功したメッセージの予約を解放します。|
|[release_ref](#release_ref)|この参照カウントを解放`choice`メッセージング ブロックします。|
|[reserve](#reserve)|これによって以前に提供されたメッセージを予約`choice`メッセージング ブロックします。|
|[unlink_target](#unlink_target)|これからのターゲット ブロックを解除`choice`メッセージング ブロックします。|
|[unlink_targets](#unlink_targets)|これからのすべてのターゲットのリンクを解除`choice`メッセージング ブロックします。 (上書き[isource::unlink_targets](isource-class.md#unlink_targets))。|
|[value](#value)|選択されたインデックスを持つメッセージを取得、`choice`メッセージング ブロックします。|

## <a name="remarks"></a>Remarks

Choice ブロックにより、受信メッセージの 1 つだけが使用されます。

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

`choice`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="accept"></a> そのまま使用します。

これによって提供されたメッセージを受け入れる`choice`ブロック、呼び出し元に所有権を転送します。

```
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

*_PTarget*<br/>
呼び出すターゲット ブロックへのポインター、`accept`メソッド。

### <a name="return-value"></a>戻り値

呼び出し元が現在の所有権を持つメッセージへのポインター。

##  <a name="acquire_ref"></a> acquire_ref

この参照カウントを取得`choice`メッセージング ブロックは、削除されないようにします。

```
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出してターゲット ブロックへのポインター。

### <a name="remarks"></a>Remarks

このメソッドを呼び出して、`ITarget`中にこのソースにリンクされているオブジェクト、`link_target`メソッド。

##  <a name="ctor"></a> 選択しました。

`choice` メッセージング ブロックを構築します。

```
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

### <a name="remarks"></a>Remarks

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

移動の構築はロックの状況では行われません。ということは、移動時に処理中の軽量タスクがないことを確認するのはユーザーの責任です。 そうしないと、例外または不整合な状態で、多数の競合が発生します。

##  <a name="dtor"></a> ~ の選択

破棄、`choice`メッセージング ブロックします。

```
~choice();
```

##  <a name="consume"></a> 使用します。

これによって以前に提供されたメッセージを使用して`choice`メッセージング ブロックと、呼び出し元に所有権を譲渡する、ターゲットが正常に予約されています。

```
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、予約済みの`message`オブジェクト。

*_PTarget*<br/>
呼び出すターゲット ブロックへのポインター、`consume`メソッド。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

### <a name="remarks"></a>Remarks

`consume`メソッドは`accept`への呼び出しでは前に必ず必要がありますが、`reserve`返さ`true`します。

##  <a name="has_value"></a> has_value

チェックするかどうかこれ`choice`メッセージング ブロックを値はまだ初期化されています。

```
bool has_value() const;

```

### <a name="return-value"></a>戻り値

`true` ブロックは、値を受け取った場合`false`それ以外の場合。

##  <a name="index"></a> インデックス

インデックスを返します、`tuple`によって選択された要素を表す、`choice`メッセージング ブロックします。

```
size_t index();
```

### <a name="return-value"></a>戻り値

メッセージのインデックス。

### <a name="remarks"></a>Remarks

使用して、メッセージ ペイロードを抽出することができます、`get`メソッド。

##  <a name="link_target"></a> link_target

このターゲット ブロックにリンク`choice`メッセージング ブロックします。

```
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
ポインター、`ITarget`ブロックにリンクするこの`choice`メッセージング ブロックします。

##  <a name="release"></a> リリース

以前に成功したメッセージの予約を解放します。

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`リリースされているオブジェクトします。

*_PTarget*<br/>
呼び出すターゲット ブロックへのポインター、`release`メソッド。

##  <a name="release_ref"></a> release_ref

この参照カウントを解放`choice`メッセージング ブロックします。

```
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出してターゲット ブロックへのポインター。

### <a name="remarks"></a>Remarks

このメソッドを呼び出して、`ITarget`このソースからリンクが解除されるオブジェクト。 ソース ブロックは、ターゲット ブロック用に予約されたリソースを解放できます。

##  <a name="reserve"></a> 予約

これによって以前に提供されたメッセージを予約`choice`メッセージング ブロックします。

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity`の`message`予約されているオブジェクトします。

*_PTarget*<br/>
呼び出すターゲット ブロックへのポインター、`reserve`メソッド。

### <a name="return-value"></a>戻り値

`true` 場合は、メッセージが正常に予約された、`false`それ以外の場合。 予約はなど、多くの理由で失敗します。 メッセージが既に予約またはソースでした、予約を拒否する、など別のターゲットによって受け入れします。

### <a name="remarks"></a>Remarks

呼び出した後`reserve`、成功した場合、いずれかを呼び出す必要があります`consume`または`release`または所有している、メッセージをそれぞれ付与するためにします。

##  <a name="unlink_target"></a> unlink_target

これからのターゲット ブロックを解除`choice`メッセージング ブロックします。

```
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
ポインター、`ITarget`これからのリンクを解除するブロック`choice`メッセージング ブロックします。

##  <a name="unlink_targets"></a> unlink_targets

これからのすべてのターゲットのリンクを解除`choice`メッセージング ブロックします。

```
virtual void unlink_targets();
```

### <a name="remarks"></a>Remarks

このメソッドがあるために、デストラクターから呼び出される必要はありません、内部のデストラクター`single_assignment`ブロックは正常に解除されます。

##  <a name="value"></a> 値

選択されたインデックスを持つメッセージを取得、`choice`メッセージング ブロックします。

```
template <
    typename _Payload_type
>
_Payload_type const& value();
```

### <a name="parameters"></a>パラメーター

*_Payload_type*<br/>
メッセージのペイロードの型。

### <a name="return-value"></a>戻り値

メッセージのペイロード。

### <a name="remarks"></a>Remarks

`choice`メッセージング ブロックは、さまざまなペイロードの種類の入力を行うことができます、取得時のペイロードの種類を指定する必要があります。 結果に基づいて、型を指定できます、`index`メソッド。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[join クラス](join-class.md)<br/>
[single_assignment クラス](single-assignment-class.md)
