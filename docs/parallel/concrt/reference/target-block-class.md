---
title: target_block クラス
ms.date: 11/04/2016
f1_keywords:
- target_block
- AGENTS/concurrency::target_block
- AGENTS/concurrency::target_block::target_block
- AGENTS/concurrency::target_block::propagate
- AGENTS/concurrency::target_block::send
- AGENTS/concurrency::target_block::async_send
- AGENTS/concurrency::target_block::decline_incoming_messages
- AGENTS/concurrency::target_block::enable_batched_processing
- AGENTS/concurrency::target_block::initialize_target
- AGENTS/concurrency::target_block::link_source
- AGENTS/concurrency::target_block::process_input_messages
- AGENTS/concurrency::target_block::process_message
- AGENTS/concurrency::target_block::propagate_message
- AGENTS/concurrency::target_block::register_filter
- AGENTS/concurrency::target_block::remove_sources
- AGENTS/concurrency::target_block::send_message
- AGENTS/concurrency::target_block::sync_send
- AGENTS/concurrency::target_block::unlink_source
- AGENTS/concurrency::target_block::unlink_sources
- AGENTS/concurrency::target_block::wait_for_async_sends
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
ms.openlocfilehash: cb8880b66ebeef12018ef7449c9c383b99ec396c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656889"
---
# <a name="targetblock-class"></a>target_block クラス

`target_block` クラスは、基本的なリンク管理機能と、ターゲットのみのブロックのエラー チェック機能を実現する抽象基底クラスです。

## <a name="syntax"></a>構文

```
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

#### <a name="parameters"></a>パラメーター

*_SourceLinkRegistry*<br/>
送信元のリンクを保持するために使用されるリンクのレジストリ。

*_MessageProcessorType*<br/>
メッセージ処理のため、プロセッサの種類。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`source_iterator`|反復子の型、`source_link_manager`この`target_block`オブジェクト。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[target_block](#ctor)|`target_block` オブジェクトを構築します。|
|[~ target_block デストラクター](#dtor)|`target_block` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[伝達](#propagate)|このターゲット ブロックにソース ブロックからメッセージを非同期的に渡します。|
|[send](#send)|このターゲット ブロックにソース ブロックからメッセージを同期的に渡します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[async_send](#async_send)|非同期処理のためのメッセージを送信します。|
|[decline_incoming_messages](#decline_incoming_messages)|ブロックに新しいメッセージを拒否することを示します。|
|[enable_batched_processing](#enable_batched_processing)|このブロックの処理のバッチ処理できます。|
|[initialize_target](#initialize_target)|ベース オブジェクトを初期化します。 具体的には、`message_processor`オブジェクトを初期化する必要があります。|
|[link_source](#link_source)|これに指定されたソース ブロックをリンク`target_block`オブジェクト。|
|[process_input_messages](#process_input_messages)|入力として受信したメッセージを処理します。|
|[process_message](#process_message)|派生クラスでオーバーライドされると、これによって承認されたメッセージを処理`target_block`オブジェクト。|
|[propagate_message](#propagate_message)|派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`このブロック`target_block`オブジェクト。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。|
|[register_filter](#register_filter)|すべての受信メッセージで呼び出されるフィルター メソッドを登録します。|
|[remove_sources](#remove_sources)|未処理の非同期送信操作が完了するを待ってから、すべてのソースをリンク解除します。|
|[send_message](#send_message)|派生クラスでオーバーライドされると、このメソッドは同期的に渡しますからのメッセージ、`ISource`このブロック`target_block`オブジェクト。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。|
|[sync_send](#sync_send)|同期的に処理するためのメッセージを送信します。|
|[unlink_source](#unlink_source)|これから指定されたソース ブロックを解除`target_block`オブジェクト。|
|[unlink_sources](#unlink_sources)|これからのすべてのソース ブロックを解除`target_block`オブジェクト。 (上書き[itarget::unlink_sources](itarget-class.md#unlink_sources))。|
|[wait_for_async_sends](#wait_for_async_sends)|非同期のすべての伝達が完了するまで待機します。|

## <a name="inheritance-hierarchy"></a>継承階層

[ITarget](itarget-class.md)

`target_block`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="async_send"></a> async_send

非同期処理のためのメッセージを送信します。

```
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
送信されるメッセージへのポインター。

##  <a name="decline_incoming_messages"></a> decline_incoming_messages

ブロックに新しいメッセージを拒否することを示します。

```
void decline_incoming_messages();
```

### <a name="remarks"></a>Remarks

このメソッドは破棄が進行中は、新しいメッセージが拒否されたことを確認するのにはデストラクターが呼び出されます。

##  <a name="enable_batched_processing"></a> enable_batched_processing

このブロックの処理のバッチ処理できます。

```
void enable_batched_processing();
```

##  <a name="initialize_target"></a> initialize_target

ベース オブジェクトを初期化します。 具体的には、`message_processor`オブジェクトを初期化する必要があります。

```
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>パラメーター

*_PScheduler*<br/>
タスクのスケジュール設定に使用するスケジューラー。

*_PScheduleGroup*<br/>
タスクのスケジュール設定に使用するスケジュール グループです。

##  <a name="link_source"></a> link_source

これに指定されたソース ブロックをリンク`target_block`オブジェクト。

```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
ポインター、`ISource`リンクするブロック。

### <a name="remarks"></a>Remarks

この関数は、上で直接呼び出されませんが、`target_block`オブジェクト。 使用してブロックを接続する必要があります、`link_target`メソッド`ISource`呼び出しは、ブロック、`link_source`メソッドを対応するターゲット。

##  <a name="process_input_messages"></a> process_input_messages

入力として受信したメッセージを処理します。

```
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
処理されるメッセージへのポインター。

##  <a name="process_message"></a> process_message

派生クラスでオーバーライドされると、これによって承認されたメッセージを処理`target_block`オブジェクト。

```
virtual void process_message(message<_Source_type> *);
```

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

メソッドはスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターが`NULL`します。

##  <a name="propagate_message"></a> propagate_message

派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`このブロック`target_block`オブジェクト。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。

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

##  <a name="register_filter"></a> register_filter

すべての受信メッセージで呼び出されるフィルター メソッドを登録します。

```
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>パラメーター

*フィルター (_f)*<br/>
フィルター メソッド。

##  <a name="remove_sources"></a> remove_sources

未処理の非同期送信操作が完了するを待ってから、すべてのソースをリンク解除します。

```
void remove_sources();
```

### <a name="remarks"></a>Remarks

すべてのターゲット ブロックには、そのデストラクターでは、ソースを削除するには、このルーチンを呼び出す必要があります。

##  <a name="send"></a> 送信

このターゲット ブロックにソース ブロックからメッセージを同期的に渡します。

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

メソッドはスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターが`NULL`します。

使用して、`send`外部メッセージの開始に使用し、ネットワーク内のメッセージを伝達するメソッドが危険であり、デッドロックが発生する可能性があります。

ときに`send`返します、メッセージが、既にされて受け入れられると、し、ターゲット ブロックに転送またはターゲットが拒否されました。

##  <a name="send_message"></a> send_message

派生クラスでオーバーライドされると、このメソッドは同期的に渡しますからのメッセージ、`ISource`このブロック`target_block`オブジェクト。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

### <a name="remarks"></a>Remarks

既定では、このブロックが返されます`declined`派生クラスでオーバーライドされない限り、します。

##  <a name="sync_send"></a> sync_send

同期的に処理するためのメッセージを送信します。

```
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
送信されるメッセージへのポインター。

##  <a name="ctor"></a> target_block

`target_block` オブジェクトを構築します。

```
target_block();
```

##  <a name="dtor"></a> ~target_block

`target_block` オブジェクトを破棄します。

```
virtual ~target_block();
```

##  <a name="unlink_source"></a> unlink_source

これから指定されたソース ブロックを解除`target_block`オブジェクト。

```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
ポインター、`ISource`リンクする場合はブロックされます。

##  <a name="unlink_sources"></a> unlink_sources

これからのすべてのソース ブロックを解除`target_block`オブジェクト。

```
virtual void unlink_sources();
```

##  <a name="wait_for_async_sends"></a> wait_for_async_sends

非同期のすべての伝達が完了するまで待機します。

```
void wait_for_async_sends();
```

### <a name="remarks"></a>Remarks

メッセージ ブロックのデストラクターはこのメソッドを使用して、すべての非同期操作には、ブロックを破棄する前に完了する時間があることを確認します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[ITarget クラス](itarget-class.md)
