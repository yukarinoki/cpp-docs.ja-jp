---
title: propagator_block クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- propagator_block
- AGENTS/concurrency::propagator_block
- AGENTS/concurrency::propagator_block::propagator_block
- AGENTS/concurrency::propagator_block::propagate
- AGENTS/concurrency::propagator_block::send
- AGENTS/concurrency::propagator_block::decline_incoming_messages
- AGENTS/concurrency::propagator_block::initialize_source_and_target
- AGENTS/concurrency::propagator_block::link_source
- AGENTS/concurrency::propagator_block::process_input_messages
- AGENTS/concurrency::propagator_block::propagate_message
- AGENTS/concurrency::propagator_block::register_filter
- AGENTS/concurrency::propagator_block::remove_network_links
- AGENTS/concurrency::propagator_block::send_message
- AGENTS/concurrency::propagator_block::unlink_source
- AGENTS/concurrency::propagator_block::unlink_sources
dev_langs:
- C++
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94fd117f43dac30aef33bef9e085f5f2fcd9d2f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376539"
---
# <a name="propagatorblock-class"></a>propagator_block クラス

`propagator_block` クラスは、ソースでもありターゲットでもあるメッセージ ブロックの抽象基底クラスです。 `source_block` クラスと `target_block` クラスの両方の機能が組み合わされています。

## <a name="syntax"></a>構文

```
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

#### <a name="parameters"></a>パラメーター

*_TargetLinkRegistry*<br/>
ターゲット リンクの保持に使用するリンクのレジストリ。

*_SourceLinkRegistry*<br/>
送信元のリンクを保持するために使用されるリンクのレジストリ。

*_MessageProcessorType*<br/>
メッセージ処理のため、プロセッサの種類。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`source_iterator`|反復子の型、`source_link_manager`この`propagator_block`します。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[propagator_block](#ctor)|`propagator_block` オブジェクトを構築します。|
|[~ propagator_block デストラクター](#dtor)|`propagator_block` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[伝達](#propagate)|このターゲット ブロックにソース ブロックからメッセージを非同期的に渡します。|
|[send](#send)|このブロックにメッセージを同期的に開始します。 メソッドを呼び出して、`ISource`ブロックします。 この関数が完了したら、メッセージは既にブロックに伝達があります。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|ブロックに新しいメッセージを拒否することを示します。|
|[initialize_source_and_target](#initialize_source_and_target)|ベース オブジェクトを初期化します。 具体的には、`message_processor`オブジェクトを初期化する必要があります。|
|[link_source](#link_source)|これに指定されたソース ブロックをリンク`propagator_block`オブジェクト。|
|[process_input_messages](#process_input_messages)|入力メッセージを処理します。 Source_block から派生する伝達子ブロックのことだけです (オーバーライド[source_block::process_input_messages](source-block-class.md#process_input_messages))。|
|[propagate_message](#propagate_message)|派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`このブロック`propagator_block`オブジェクト。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。|
|[register_filter](#register_filter)|すべての受信メッセージで呼び出されるフィルター メソッドを登録します。|
|[remove_network_links](#remove_network_links)|これからすべてのソースとターゲット ネットワーク リンクを削除します。`propagator_block`オブジェクト。|
|[send_message](#send_message)|派生クラスでオーバーライドされると、このメソッドは同期的に渡しますからのメッセージ、`ISource`このブロック`propagator_block`オブジェクト。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。|
|[unlink_source](#unlink_source)|これから指定されたソース ブロックを解除`propagator_block`オブジェクト。|
|[unlink_sources](#unlink_sources)|これからのすべてのソース ブロックを解除`propagator_block`オブジェクト。 (上書き[itarget::unlink_sources](itarget-class.md#unlink_sources))。|

## <a name="remarks"></a>Remarks

複数の継承を回避するために、`propagator_block`クラスから継承、`source_block`クラスと`ITarget`抽象クラス。 ほとんどの機能の`target_block`クラスはここでレプリケートされます。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="decline_incoming_messages"></a> decline_incoming_messages

ブロックに新しいメッセージを拒否することを示します。

```
void decline_incoming_messages();
```

### <a name="remarks"></a>Remarks

このメソッドは破棄が進行中は、新しいメッセージが拒否されたことを確認するのにはデストラクターが呼び出されます。

##  <a name="initialize_source_and_target"></a> initialize_source_and_target

ベース オブジェクトを初期化します。 具体的には、`message_processor`オブジェクトを初期化する必要があります。

```
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>パラメーター

*_PScheduler*<br/>
タスクのスケジュール設定に使用するスケジューラー。

*_PScheduleGroup*<br/>
タスクのスケジュール設定に使用するスケジュール グループです。

##  <a name="link_source"></a> link_source

これに指定されたソース ブロックをリンク`propagator_block`オブジェクト。

```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
ポインター、`ISource`リンクするブロック。

##  <a name="process_input_messages"></a> process_input_messages

入力メッセージを処理します。 Source_block から派生する伝達子ブロックのことだけです。

```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
処理されるメッセージへのポインター。

##  <a name="propagate"></a> 伝達

このターゲット ブロックにソース ブロックからメッセージを非同期的に渡します。

```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

### <a name="remarks"></a>Remarks

`propagate`リンクのソース ブロックからのターゲット ブロックにメソッドが呼び出されます。 1 つは、既にキューにない場合、メッセージを処理する非同期タスクまたは実行をキューに入れます。

メソッドはスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターが`NULL`します。

##  <a name="propagate_message"></a> propagate_message

派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`このブロック`propagator_block`オブジェクト。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

##  <a name="ctor"></a> propagator_block

`propagator_block` オブジェクトを構築します。

```
propagator_block();
```

##  <a name="dtor"></a> ~propagator_block

`propagator_block` オブジェクトを破棄します。

```
virtual ~propagator_block();
```

##  <a name="register_filter"></a> register_filter

すべての受信メッセージで呼び出されるフィルター メソッドを登録します。

```
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>パラメーター

*フィルター (_f)*<br/>
フィルター メソッド。

##  <a name="remove_network_links"></a> remove_network_links

これからすべてのソースとターゲット ネットワーク リンクを削除します。`propagator_block`オブジェクト。

```
void remove_network_links();
```

##  <a name="send"></a> 送信

このブロックにメッセージを同期的に開始します。 メソッドを呼び出して、`ISource`ブロックします。 この関数が完了したら、メッセージは既にブロックに伝達があります。

```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

### <a name="remarks"></a>Remarks

このメソッドは、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターが`NULL`します。

##  <a name="send_message"></a> send_message

派生クラスでオーバーライドされると、このメソッドは同期的に渡しますからのメッセージ、`ISource`このブロック`propagator_block`オブジェクト。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

### <a name="remarks"></a>Remarks

既定では、このブロックが返されます`declined`派生クラスでオーバーライドされない限り、します。

##  <a name="unlink_source"></a> unlink_source

これから指定されたソース ブロックを解除`propagator_block`オブジェクト。

```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
ポインター、`ISource`リンクする場合はブロックされます。

##  <a name="unlink_sources"></a> unlink_sources

これからのすべてのソース ブロックを解除`propagator_block`オブジェクト。

```
virtual void unlink_sources();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[source_block クラス](source-block-class.md)<br/>
[ITarget クラス](itarget-class.md)
