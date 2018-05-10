---
title: source_block クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 64b9873ef6da00b4ef0fb03e43f61fa704484389
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="sourceblock-class"></a>source_block クラス
`source_block` クラスは、ソースのみのブロックの抽象基底クラスです。 このクラスには、基本的なリンク管理機能および一般的なエラー チェック機能が用意されています。  
  
## <a name="syntax"></a>構文  
  
```
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_TargetLinkRegistry`  
 ターゲット リンクの保持に使用するレジストリをリンクします。  
  
 `_MessageProcessorType`  
 メッセージ処理のプロセッサの種類。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`target_iterator`|接続されているターゲットを段階的に反復子。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[source_block](#ctor)|`source_block` オブジェクトを構築します。|  
|[~ source_block デストラクター](#dtor)|`source_block` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept](#accept)|これによって提供されたメッセージを受け入れる`source_block`呼び出し元に所有権を転送するオブジェクト。|  
|[acquire_ref](#acquire_ref)|この参照カウントを取得`source_block`オブジェクト、削除を禁止します。|  
|[使用します。](#consume)|これによって以前に提供メッセージを使用して`source_block`オブジェクトし、呼び出し元に所有権を転送する、ターゲットが正常に予約されています。|  
|[link_target](#link_target)|これをターゲット ブロックをリンク`source_block`オブジェクト。|  
|[release](#release)|以前に成功したメッセージの予約を解放します。|  
|[release_ref](#release_ref)|この参照カウントを解放`source_block`オブジェクト。|  
|[reserve](#reserve)|これによって以前に提供メッセージを予約`source_block`オブジェクト。|  
|[unlink_target](#unlink_target)|ターゲット ブロックをこれからのリンクを解除`source_block`オブジェクト。|  
|[unlink_targets](#unlink_targets)|これからすべてのターゲット ブロックのリンクを解除`source_block`オブジェクト。 (上書き[isource::unlink_targets](isource-class.md#unlink_targets))。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept_message](#accept_message)|派生クラスでオーバーライドされると、ソースによって提供されたメッセージを受け入れます。 メッセージ ブロックは、検証するには、このメソッドをオーバーライドする必要があります、`_MsgId`し、メッセージが返されます。|  
|[async_send](#async_send)|非同期的にメッセージをキューに配置しがまだ実行されている場合、伝達のタスクを開始|  
|[consume_message](#consume_message)|派生クラスでオーバーライドされると、以前に予約されたメッセージを消費します。|  
|[enable_batched_processing](#enable_batched_processing)|有効では、このブロックの処理をバッチ処理します。|  
|[initialize_source](#initialize_source)|初期化、`message_propagator`この`source_block`です。|  
|[link_target_notification](#link_target_notification)|新しいターゲットがこれにリンクされていることを通知するコールバック`source_block`オブジェクト。|  
|[process_input_messages](#process_input_messages)|入力メッセージを処理します。 これは伝達子ブロック、source_block から派生するのに役立ちます|  
|[propagate_output_messages](#propagate_output_messages)|ターゲットにメッセージを伝達します。|  
|[propagate_to_any_targets](#propagate_to_any_targets)|派生クラスでオーバーライドされると、一部またはすべてのリンクのターゲットに指定されたメッセージを伝達します。 これは、メッセージ ブロックの主要な伝達ルーチンです。|  
|[release_message](#release_message)|派生クラスでオーバーライドされると、以前のメッセージの予約を解放します。|  
|[remove_targets](#remove_targets)|このソース ブロックのすべての送信先のリンクを削除します。 これは、デストラクターから呼び出される必要があります。|  
|[reserve_message](#reserve_message)|派生クラスでオーバーライドされると、これによって以前に提供メッセージを予約`source_block`オブジェクト。|  
|[resume_propagation](#resume_propagation)|派生クラスでオーバーライドされると、予約が解放された後に伝達を再開します。|  
|[sync_send](#sync_send)|同期的にメッセージをキューに登録しがまだ実行されている場合は、伝達のタスクを開始します。|  
|[unlink_target_notification](#unlink_target_notification)|ターゲットがこれからリンクされていることを通知するコールバック`source_block`オブジェクト。|  
|[wait_for_outstanding_async_sends](#wait_for_outstanding_async_sends)|非同期のすべての伝達が完了するまで待機します。 この伝達子に固有のスピン待機は、すべての非同期伝達にブロックを破棄する前に完了するのに時間があることを確認するメッセージ ブロックのデストラクターで使用されます。|  
  
## <a name="remarks"></a>コメント  
 メッセージ ブロックは、リンクの管理とこのクラスによって提供される同期を活用するには、このブロックから派生する必要があります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 `source_block`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="accept"></a> そのまま使用します。 

 これによって提供されたメッセージを受け入れる`source_block`呼び出し元に所有権を転送するオブジェクト。  
  
```
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`accept`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`呼び出し元がの所有権をオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`します。  
  
 `accept`メソッドは、メッセージは、これによって提供されているときに、ターゲットによって呼び出されます。`ISource`ブロックします。 返されるメッセージ ポインターに渡されたものと異なる場合があります、`propagate`のメソッド、`ITarget`メッセージのコピーを作成する場合はこのソースをブロックします。  
  
##  <a name="accept_message"></a> accept_message 

 派生クラスでオーバーライドされると、ソースによって提供されたメッセージを受け入れます。 メッセージ ブロックは、検証するには、このメソッドをオーバーライドする必要があります、`_MsgId`し、メッセージが返されます。  
  
```
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 ランタイム オブジェクト id、`message`オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 呼び出し元は、現在の所有権を持つメッセージへのポインター。  
  
### <a name="remarks"></a>コメント  
 所有権を譲渡するには、元のメッセージ ポインターが返されます。 所有権を保持するには、メッセージ ペイロードのコピーが作成され、返される必要があります。  
  
##  <a name="acquire_ref"></a> acquire_ref 

 この参照カウントを取得`source_block`オブジェクト、削除を禁止します。  
  
```
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`中にこのソースにリンクされているオブジェクト、`link_target`メソッドです。  
  
##  <a name="async_send"></a> async_send 

 非同期的にメッセージをキューに配置しがまだ実行されている場合、伝達のタスクを開始  
  
```
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 ポインター、`message`非同期的に送信するオブジェクト。  
  
##  <a name="consume"></a> 使用します。 

 これによって以前に提供メッセージを使用して`source_block`オブジェクトし、呼び出し元に所有権を転送する、ターゲットが正常に予約されています。  
  
```
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、予約済みの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`consume`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`呼び出し元がの所有権をオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`します。  
  
 メソッドをスロー、 [bad_target](bad-target-class.md)例外場合パラメーター`_PTarget`と呼ばれる、ターゲットを表さない`reserve`です。  
  
 `consume`メソッドは`accept`への呼び出しでは前に必ず必要がありますが、`reserve`返さ`true`です。  
  
##  <a name="consume_message"></a> consume_message 

 派生クラスでオーバーライドされると、以前に予約されたメッセージを消費します。  
  
```
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`使用されているオブジェクトします。  
  
### <a name="return-value"></a>戻り値  
 呼び出し元は、現在の所有権を持つメッセージへのポインター。  
  
### <a name="remarks"></a>コメント  
 ような`accept`への呼び出し前に常に、`reserve`です。  
  
##  <a name="enable_batched_processing"></a> enable_batched_processing 

 有効では、このブロックの処理をバッチ処理します。  
  
```
void enable_batched_processing();
```  
  
##  <a name="initialize_source"></a> initialize_source 

 初期化、`message_propagator`この`source_block`です。  
  
```
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PScheduler`  
 タスクのスケジューリングに使用するスケジューラー。  
  
 `_PScheduleGroup`  
 タスクのスケジューリングに使用するスケジュール グループ。  
  
##  <a name="link_target"></a> link_target 

 これをターゲット ブロックをリンク`source_block`オブジェクト。  
  
```
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`ブロックをこのリンクを`source_block`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`します。  
  
##  <a name="link_target_notification"></a> link_target_notification 

 新しいターゲットがこれにリンクされていることを通知するコールバック`source_block`オブジェクト。  
  
```
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```  
  
##  <a name="process_input_messages"></a> process_input_messages 

 入力メッセージを処理します。 これは伝達子ブロック、source_block から派生するのに役立ちます  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
  
##  <a name="propagate_output_messages"></a> propagate_output_messages 

 ターゲットにメッセージを伝達します。  
  
```
virtual void propagate_output_messages();
```  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 派生クラスでオーバーライドされると、一部またはすべてのリンクのターゲットに指定されたメッセージを伝達します。 これは、メッセージ ブロックの主要な伝達ルーチンです。  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 反映するのには、メッセージへのポインター。  
  
##  <a name="release"></a> リリース 

 以前に成功したメッセージの予約を解放します。  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、予約済みの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`release`メソッドです。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`します。  
  
 メソッドをスロー、 [bad_target](bad-target-class.md)例外場合パラメーター`_PTarget`と呼ばれる、ターゲットを表さない`reserve`です。  
  
##  <a name="release_message"></a> release_message 

 派生クラスでオーバーライドされると、以前のメッセージの予約を解放します。  
  
```
virtual void release_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
##  <a name="release_ref"></a> release_ref 

 この参照カウントを解放`source_block`オブジェクト。  
  
```
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出すターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`このソースからリンクが解除されるオブジェクト。 ソース ブロックがターゲット ブロック用に予約されたリソースを解放する許可されます。  
  
##  <a name="remove_targets"></a> remove_targets 

 このソース ブロックのすべての送信先のリンクを削除します。 これは、デストラクターから呼び出される必要があります。  
  
```
void remove_targets();
```  
  
##  <a name="reserve"></a> 予約 

 これによって以前に提供メッセージを予約`source_block`オブジェクト。  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`reserve`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 `true` 場合は、メッセージが正常に予約された、`false`それ以外の場合。 予約は、さまざまな理由で失敗することが: メッセージが既に予約か、またはソースでした、予約を拒否するなど、別のターゲットで受け入れられます。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`します。  
  
 呼び出した後`reserve`、成功した場合、いずれかを呼び出す必要があります`consume`または`release`かかるまたは所有している、メッセージをそれぞれ付与するためにします。  
  
##  <a name="reserve_message"></a> reserve_message 

 派生クラスでオーバーライドされると、これによって以前に提供メッセージを予約`source_block`オブジェクト。  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`オブジェクトの中に予約されています。  
  
### <a name="return-value"></a>戻り値  
 `true` 場合は、メッセージが正常に予約された、`false`それ以外の場合。  
  
### <a name="remarks"></a>コメント  
 後に`reserve`と呼ばれる場合は、返された場合`true`か、`consume`または`release`かかるか、メッセージの所有権を解放を呼び出す必要があります。  
  
##  <a name="resume_propagation"></a> resume_propagation 

 派生クラスでオーバーライドされると、予約が解放された後に伝達を再開します。  
  
```
virtual void resume_propagation() = 0;
```  
  
##  <a name="ctor"></a> source_block 

 `source_block` オブジェクトを構築します。  
  
```
source_block();
```  
  
##  <a name="dtor"></a> ~source_block 

 `source_block` オブジェクトを破棄します。  
  
```
virtual ~source_block();
```  
  
##  <a name="sync_send"></a> sync_send 

 同期的にメッセージをキューに登録しがまだ実行されている場合は、伝達のタスクを開始します。  
  
```
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 ポインター、`message`同期的に送信するオブジェクト。  
  
##  <a name="unlink_target"></a> unlink_target 

 ターゲット ブロックをこれからのリンクを解除`source_block`オブジェクト。  
  
```
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`このリンクを解除するブロック`source_block`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 メソッドをスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_PTarget`は`NULL`します。  
  
##  <a name="unlink_target_notification"></a> unlink_target_notification 

 ターゲットがこれからリンクされていることを通知するコールバック`source_block`オブジェクト。  
  
```
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 `ITarget`ブロックをリンクが解除されました。  
  
##  <a name="unlink_targets"></a> unlink_targets 

 これからすべてのターゲット ブロックのリンクを解除`source_block`オブジェクト。  
  
```
virtual void unlink_targets();
```  
  
##  <a name="wait_for_outstanding_async_sends"></a> wait_for_outstanding_async_sends 

 非同期のすべての伝達が完了するまで待機します。 この伝達子に固有のスピン待機は、すべての非同期伝達にブロックを破棄する前に完了するのに時間があることを確認するメッセージ ブロックのデストラクターで使用されます。  
  
```
void wait_for_outstanding_async_sends();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ISource クラス](isource-class.md)
