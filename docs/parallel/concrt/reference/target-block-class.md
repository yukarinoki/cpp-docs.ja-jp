---
title: target_block クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 754bc6add99974ff204c977e47f35486cc830d95
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="targetblock-class"></a>target_block クラス
`target_block` クラスは、基本的なリンク管理機能と、ターゲットのみのブロックのエラー チェック機能を実現する抽象基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_SourceLinkRegistry`  
 送信元のリンクを保持するために使用されるリンク レジストリです。  
  
 `_MessageProcessorType`  
 メッセージ処理のプロセッサの種類。  
  
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
|[enable_batched_processing](#enable_batched_processing)|有効では、このブロックの処理をバッチ処理します。|  
|[initialize_target](#initialize_target)|ベース オブジェクトを初期化します。 具体的には、`message_processor`オブジェクトを初期化する必要があります。|  
|[link_source](#link_source)|これを指定されたソース ブロックをリンク`target_block`オブジェクト。|  
|[process_input_messages](#process_input_messages)|入力として受信したメッセージを処理します。|  
|[process_message](#process_message)|派生クラスでオーバーライドされると、これによって承認されたメッセージを処理`target_block`オブジェクト。|  
|[propagate_message](#propagate_message)|派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`ブロックをこの`target_block`オブジェクト。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[register_filter](#register_filter)|すべての受信メッセージで呼び出されるフィルター メソッドを登録します。|  
|[remove_sources](#remove_sources)|未処理の非同期送信操作の完了を待機した後にすべてのソースのリンクを解除します。|  
|[send_message](#send_message)|派生クラスでオーバーライドされると、このメソッドは同期的に渡しますからのメッセージ、`ISource`ブロックをこの`target_block`オブジェクト。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[sync_send](#sync_send)|同期的に処理するためのメッセージを送信します。|  
|[unlink_source](#unlink_source)|これから指定されたソース ブロックのリンクを解除`target_block`オブジェクト。|  
|[unlink_sources](#unlink_sources)|これからすべてのソース ブロックのリンクを解除`target_block`オブジェクト。 (上書き[itarget::unlink_sources](itarget-class.md#unlink_sources))。|  
|[wait_for_async_sends](#wait_for_async_sends)|非同期のすべての伝達が完了するまで待機します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ITarget](itarget-class.md)  
  
 `target_block`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="async_send"></a> async_send 

 非同期処理のためのメッセージを送信します。  
  
```
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 送信されるメッセージへのポインター。  
  
##  <a name="decline_incoming_messages"></a> decline_incoming_messages 

 ブロックに新しいメッセージを拒否することを示します。  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、デストラクターが破棄が進行中は、新しいメッセージが却下されたことを確認してください。  
  
##  <a name="enable_batched_processing"></a> enable_batched_processing 

 有効では、このブロックの処理をバッチ処理します。  
  
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
 `_PScheduler`  
 タスクのスケジューリングに使用するスケジューラー。  
  
 `_PScheduleGroup`  
 タスクのスケジューリングに使用するスケジュール グループ。  
  
##  <a name="link_source"></a> link_source 

 これを指定されたソース ブロックをリンク`target_block`オブジェクト。  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PSource`  
 ポインター、`ISource`リンクするのには、ブロックします。  
  
### <a name="remarks"></a>コメント  
 この関数は、上で直接呼び出すことはできません、`target_block`オブジェクト。 使用してブロックを接続する必要があります、`link_target`メソッドを`ISource`呼び出しは、ブロック、`link_source`対応するターゲットのメソッドです。  
  
##  <a name="process_input_messages"></a> process_input_messages 

 入力として受信したメッセージを処理します。  
  
```
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
  
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
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)のメッセージを行うには、対象の決定を示す値。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターは`NULL`します。  
  
##  <a name="propagate_message"></a> propagate_message 

 派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`ブロックをこの`target_block`オブジェクト。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)のメッセージを行うには、対象の決定を示す値。  
  
##  <a name="register_filter"></a> register_filter 

 すべての受信メッセージで呼び出されるフィルター メソッドを登録します。  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Filter`  
 フィルター メソッド。  
  
##  <a name="remove_sources"></a> remove_sources 

 未処理の非同期送信操作の完了を待機した後にすべてのソースのリンクを解除します。  
  
```
void remove_sources();
```  
  
### <a name="remarks"></a>コメント  
 すべてのターゲット ブロックには、デストラクター内のソースを削除するには、このルーチンを呼び出す必要があります。  
  
##  <a name="send"></a> 送信 

 このターゲット ブロックにソース ブロックからメッセージを同期的に渡します。  
  
```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)のメッセージを行うには、対象の決定を示す値。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターは`NULL`します。  
  
 使用して、`send`開始に使用するメッセージの外部でと、ネットワーク内でメッセージを伝達する方法が危険であり、デッドロックにつながることができます。  
  
 ときに`send`を返します、メッセージが、既にされて受け入れられたら、し、ターゲット ブロックに転送、または、ターゲットが拒否されました。  
  
##  <a name="send_message"></a> send_message 

 派生クラスでオーバーライドされると、このメソッドは同期的に渡しますからのメッセージ、`ISource`ブロックをこの`target_block`オブジェクト。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)のメッセージを行うには、対象の決定を示す値。  
  
### <a name="remarks"></a>コメント  
 既定では、このブロックを返します`declined`派生クラスでオーバーライドされない限り、します。  
  
##  <a name="sync_send"></a> sync_send 

 同期的に処理するためのメッセージを送信します。  
  
```
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
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

 これから指定されたソース ブロックのリンクを解除`target_block`オブジェクト。  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PSource`  
 ポインター、`ISource`リンクを解除するのには、ブロックします。  
  
##  <a name="unlink_sources"></a> unlink_sources 

 これからすべてのソース ブロックのリンクを解除`target_block`オブジェクト。  
  
```
virtual void unlink_sources();
```  
  
##  <a name="wait_for_async_sends"></a> wait_for_async_sends 

 非同期のすべての伝達が完了するまで待機します。  
  
```
void wait_for_async_sends();
```  
  
### <a name="remarks"></a>コメント  
 メッセージ ブロックのデストラクターはこのメソッドを使用して、すべての非同期操作がブロックを破棄する前に完了する時間を確認します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ITarget クラス](itarget-class.md)
