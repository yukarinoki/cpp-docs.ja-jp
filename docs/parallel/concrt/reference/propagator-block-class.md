---
description: '詳細情報: propagator_block クラス'
title: propagator_block クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
ms.openlocfilehash: 4dd006829e01f663be20be76a2cc2e0364ef7b38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115262"
---
# <a name="propagator_block-class"></a>propagator_block クラス

`propagator_block` クラスは、ソースでもありターゲットでもあるメッセージ ブロックの抽象基底クラスです。 `source_block` クラスと `target_block` クラスの両方の機能が組み合わされています。

## <a name="syntax"></a>構文

```cpp
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>パラメーター

*_TargetLinkRegistry*<br/>
ターゲットリンクを保持するために使用されるリンクレジストリ。

*_SourceLinkRegistry*<br/>
ソースリンクを保持するために使用されるリンクレジストリ。

*_MessageProcessorType*<br/>
メッセージ処理のプロセッサの種類。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`source_iterator`|こののの反復子の型 `source_link_manager` `propagator_block` 。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[propagator_block](#ctor)|`propagator_block` オブジェクトを構築します。|
|[~ propagator_block デストラクター](#dtor)|`propagator_block` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[伝](#propagate)|ソースブロックからこのターゲットブロックにメッセージを非同期的に渡します。|
|[送信](#send)|このブロックへのメッセージを同期的に開始します。 ブロックによって呼び出され `ISource` ます。 この関数が完了すると、メッセージは既にブロックに反映されています。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|新しいメッセージを拒否するブロックを示します。|
|[initialize_source_and_target](#initialize_source_and_target)|基本オブジェクトを初期化します。 具体的には、 `message_processor` オブジェクトを初期化する必要があります。|
|[link_source](#link_source)|指定されたソースブロックをこのオブジェクトにリンク `propagator_block` します。|
|[process_input_messages](#process_input_messages)|入力メッセージを処理します。 これは、source_block から派生した伝達子ブロックにのみ有効です ( [source_block::p rocess_input_messages](source-block-class.md#process_input_messages)をオーバーライドします)。|
|[propagate_message](#propagate_message)|派生クラスでオーバーライドされた場合、このメソッドは、ブロックからこのオブジェクトにメッセージを非同期的に渡し `ISource` `propagator_block` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[register_filter](#register_filter)|受信したすべてのメッセージに対して呼び出されるフィルターメソッドを登録します。|
|[remove_network_links](#remove_network_links)|このオブジェクトから、ソースとターゲットのネットワークリンクをすべて削除し `propagator_block` ます。|
|[send_message](#send_message)|派生クラスでオーバーライドされた場合、このメソッドは、ブロックからこのオブジェクトにメッセージを同期的に渡し `ISource` `propagator_block` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[unlink_source](#unlink_source)|指定したソースブロックをこのオブジェクトからリンク解除 `propagator_block` します。|
|[unlink_sources](#unlink_sources)|このオブジェクトからすべてのソースブロックのリンクを解除 `propagator_block` します。 ( [ITarget:: unlink_sources](itarget-class.md#unlink_sources)よりも優先されます)。|

## <a name="remarks"></a>解説

複数の継承を避けるために、クラスは `propagator_block` `source_block` クラスと `ITarget` 抽象クラスから継承します。 クラスのほとんどの機能 `target_block` はここでレプリケートされます。

## <a name="inheritance-hierarchy"></a>継承階層

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="decline_incoming_messages"></a><a name="decline_incoming_messages"></a> decline_incoming_messages

新しいメッセージを拒否するブロックを示します。

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>解説

このメソッドは、破棄の実行中に新しいメッセージが拒否されるようにするために、デストラクターによって呼び出されます。

## <a name="initialize_source_and_target"></a><a name="initialize_source_and_target"></a> initialize_source_and_target

基本オブジェクトを初期化します。 具体的には、 `message_processor` オブジェクトを初期化する必要があります。

```cpp
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>パラメーター

*_PScheduler*<br/>
タスクをスケジュールするために使用するスケジューラ。

*_PScheduleGroup*<br/>
タスクをスケジュールするために使用されるスケジュールグループ。

## <a name="link_source"></a><a name="link_source"></a> link_source

指定されたソースブロックをこのオブジェクトにリンク `propagator_block` します。

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
リンクされるブロックへのポインター `ISource` 。

## <a name="process_input_messages"></a><a name="process_input_messages"></a> process_input_messages

入力メッセージを処理します。 これは、から派生した伝達子ブロックにのみ有効です source_block

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
処理するメッセージへのポインター。

## <a name="propagate"></a><a name="propagate"></a> 伝

ソースブロックからこのターゲットブロックにメッセージを非同期的に渡します。

```cpp
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した [message_status](concurrency-namespace-enums.md) を示します。

### <a name="remarks"></a>解説

メソッドは、 `propagate` リンクされたソースブロックによってターゲットブロックで呼び出されます。 メッセージがまだキューに登録されていない場合、または実行中でない場合は、非同期タスクをキューに配置してメッセージを処理します。

パラメーターまたはパラメーターのいずれかがの場合、メソッドは [invalid_argument](../../../standard-library/invalid-argument-class.md) 例外をスローし `_PMessage` `_PSource` `NULL` ます。

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

派生クラスでオーバーライドされた場合、このメソッドは、ブロックからこのオブジェクトにメッセージを非同期的に渡し `ISource` `propagator_block` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した [message_status](concurrency-namespace-enums.md) を示します。

## <a name="propagator_block"></a><a name="ctor"></a> propagator_block

`propagator_block` オブジェクトを構築します。

```cpp
propagator_block();
```

## <a name="propagator_block"></a><a name="dtor"></a> ~ propagator_block

`propagator_block` オブジェクトを破棄します。

```cpp
virtual ~propagator_block();
```

## <a name="register_filter"></a><a name="register_filter"></a> register_filter

受信したすべてのメッセージに対して呼び出されるフィルターメソッドを登録します。

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>パラメーター

*_Filter*<br/>
フィルターメソッド。

## <a name="remove_network_links"></a><a name="remove_network_links"></a> remove_network_links

このオブジェクトから、ソースとターゲットのネットワークリンクをすべて削除し `propagator_block` ます。

```cpp
void remove_network_links();
```

## <a name="send"></a><a name="send"></a> 送信

このブロックへのメッセージを同期的に開始します。 ブロックによって呼び出され `ISource` ます。 この関数が完了すると、メッセージは既にブロックに反映されています。

```cpp
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した [message_status](concurrency-namespace-enums.md) を示します。

### <a name="remarks"></a>解説

パラメーターまたはパラメーターのいずれかがの場合、このメソッドは [invalid_argument](../../../standard-library/invalid-argument-class.md) 例外をスロー `_PMessage` `_PSource` `NULL` します。

## <a name="send_message"></a><a name="send_message"></a> send_message

派生クラスでオーバーライドされた場合、このメソッドは、ブロックからこのオブジェクトにメッセージを同期的に渡し `ISource` `propagator_block` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した [message_status](concurrency-namespace-enums.md) を示します。

### <a name="remarks"></a>解説

既定では、 `declined` 派生クラスによってオーバーライドされない限り、このブロックはを返します。

## <a name="unlink_source"></a><a name="unlink_source"></a> unlink_source

指定したソースブロックをこのオブジェクトからリンク解除 `propagator_block` します。

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
リンク解除するブロックへのポインター `ISource` 。

## <a name="unlink_sources"></a><a name="unlink_sources"></a> unlink_sources

このオブジェクトからすべてのソースブロックのリンクを解除 `propagator_block` します。

```cpp
virtual void unlink_sources();
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[source_block クラス](source-block-class.md)<br/>
[ITarget クラス](itarget-class.md)
