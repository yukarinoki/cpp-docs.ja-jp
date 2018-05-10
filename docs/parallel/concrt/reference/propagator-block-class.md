---
title: propagator_block クラス |Microsoft ドキュメント
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
ms.openlocfilehash: eb908bf108bb3ddff375506225b9be97b2898ca5
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
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
 `_TargetLinkRegistry`  
 ターゲット リンクの保持に使用するリンク レジストリです。  
  
 `_SourceLinkRegistry`  
 送信元のリンクを保持するために使用されるリンク レジストリです。  
  
 `_MessageProcessorType`  
 メッセージ処理のプロセッサの種類。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`source_iterator`|反復子の型、`source_link_manager`この`propagator_block`です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[propagator_block](#ctor)|`propagator_block` オブジェクトを構築します。|  
|[~ propagator_block デストラクター](#dtor)|`propagator_block` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[伝達](#propagate)|このターゲット ブロックにソース ブロックからメッセージを非同期的に渡します。|  
|[send](#send)|このブロックにメッセージを同期的に処理を開始します。 によって呼び出される、`ISource`ブロックします。 この関数が完了したら、メッセージは既にブロックに伝達がします。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[decline_incoming_messages](#decline_incoming_messages)|ブロックに新しいメッセージを拒否することを示します。|  
|[initialize_source_and_target](#initialize_source_and_target)|ベース オブジェクトを初期化します。 具体的には、`message_processor`オブジェクトを初期化する必要があります。|  
|[link_source](#link_source)|これを指定されたソース ブロックをリンク`propagator_block`オブジェクト。|  
|[process_input_messages](#process_input_messages)|入力メッセージを処理します。 これは伝達子ブロック、source_block から派生するのに便利です (オーバーライド[source_block::process_input_messages](source-block-class.md#process_input_messages))。|  
|[propagate_message](#propagate_message)|派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`ブロックをこの`propagator_block`オブジェクト。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[register_filter](#register_filter)|すべての受信メッセージで呼び出されるフィルター メソッドを登録します。|  
|[remove_network_links](#remove_network_links)|これからすべてのソースとターゲット ネットワーク リンクを削除`propagator_block`オブジェクト。|  
|[send_message](#send_message)|派生クラスでオーバーライドされると、このメソッドは同期的に渡しますからのメッセージ、`ISource`ブロックをこの`propagator_block`オブジェクト。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[unlink_source](#unlink_source)|これから指定されたソース ブロックのリンクを解除`propagator_block`オブジェクト。|  
|[unlink_sources](#unlink_sources)|これからすべてのソース ブロックのリンクを解除`propagator_block`オブジェクト。 (上書き[itarget::unlink_sources](itarget-class.md#unlink_sources))。|  
  
## <a name="remarks"></a>コメント  
 複数の継承を避けるために、`propagator_block`クラスから継承、`source_block`クラスと`ITarget`抽象クラスです。 機能のほとんどの`target_block`クラスはここでレプリケートします。  
  
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
  
### <a name="remarks"></a>コメント  
 このメソッドは、デストラクターが破棄が進行中は、新しいメッセージが却下されたことを確認してください。  
  
##  <a name="initialize_source_and_target"></a> initialize_source_and_target 

 ベース オブジェクトを初期化します。 具体的には、`message_processor`オブジェクトを初期化する必要があります。  
  
```
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PScheduler`  
 タスクのスケジューリングに使用するスケジューラー。  
  
 `_PScheduleGroup`  
 タスクのスケジューリングに使用するスケジュール グループ。  
  
##  <a name="link_source"></a> link_source 

 これを指定されたソース ブロックをリンク`propagator_block`オブジェクト。  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PSource`  
 ポインター、`ISource`リンクするのには、ブロックします。  
  
##  <a name="process_input_messages"></a> process_input_messages 

 入力メッセージを処理します。 これは伝達子ブロック、source_block から派生するのに役立ちます  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
  
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
 `propagate`メソッドは、リンクのソース ブロックがターゲット ブロックで呼び出されます。 既にキューがない場合、メッセージを処理する非同期タスクまたは実行をキューに入れます。  
  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターは`NULL`します。  
  
##  <a name="propagate_message"></a> propagate_message 

 派生クラスでオーバーライドされると、このメソッドは非同期的に渡しますからのメッセージ、`ISource`ブロックをこの`propagator_block`オブジェクト。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
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
 `_Filter`  
 フィルター メソッド。  
  
##  <a name="remove_network_links"></a> remove_network_links 

 これからすべてのソースとターゲット ネットワーク リンクを削除`propagator_block`オブジェクト。  
  
```
void remove_network_links();
```  
  
##  <a name="send"></a> 送信 

 このブロックにメッセージを同期的に処理を開始します。 によって呼び出される、`ISource`ブロックします。 この関数が完了したら、メッセージは既にブロックに伝達がします。  
  
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
 このメソッドは、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターは`NULL`します。  
  
##  <a name="send_message"></a> send_message 

 派生クラスでオーバーライドされると、このメソッドは同期的に渡しますからのメッセージ、`ISource`ブロックをこの`propagator_block`オブジェクト。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)のメッセージを行うには、対象の決定を示す値。  
  
### <a name="remarks"></a>コメント  
 既定では、このブロックを返します`declined`派生クラスでオーバーライドされない限り、します。  
  
##  <a name="unlink_source"></a> unlink_source 

 これから指定されたソース ブロックのリンクを解除`propagator_block`オブジェクト。  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PSource`  
 ポインター、`ISource`リンクを解除するのには、ブロックします。  
  
##  <a name="unlink_sources"></a> unlink_sources 

 これからすべてのソース ブロックのリンクを解除`propagator_block`オブジェクト。  
  
```
virtual void unlink_sources();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [source_block クラス](source-block-class.md)   
 [ITarget クラス](itarget-class.md)
