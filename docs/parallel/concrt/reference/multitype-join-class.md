---
title: multitype_join クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e91080621fbaec089079cad6e2a3c8d32e6cfacb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692491"
---
# <a name="multitypejoin-class"></a>multitype_join クラス
`multitype_join` メッセージング ブロックは、複数のソースと単一のターゲットを持つメッセージング ブロックで、それぞれのソースから受け取った異なる種類のメッセージを 1 つに結合してターゲットに渡します。  
  
## <a name="syntax"></a>構文  
  
```  
template<
    typename T,  
    join_type _Jtype = non_greedy  
>  
class multitype_join: public ISource<typename _Unwrap<T>::type>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 `tuple`メッセージのペイロードの種類に参加しているし、ブロックによって反映されます。  
  
 `_Jtype`  
 種類の`join`ブロックするか、これは`greedy`または `non_greedy`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`type`|型の別名`T`です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[multitype_join](#ctor)|オーバーロードされます。 `multitype_join` メッセージング ブロックを構築します。|  
|[~ multitype_join デストラクター](#dtor)|破棄、`multitype_join`メッセージング ブロックです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept](#accept)|これによって提供されたメッセージを受け入れる`multitype_join`ブロック、呼び出し元に所有権を転送します。|  
|[acquire_ref](#acquire_ref)|この参照カウントを獲得`multitype_join`メッセージング ブロックを削除されないようにします。|  
|[使用します。](#consume)|によって以前に提供メッセージを使用して、`multitype_join`ブロックのメッセージングおよび呼び出し元に所有権を転送する、ターゲットが正常に予約されています。|  
|[link_target](#link_target)|これをターゲット ブロックをリンク`multitype_join`メッセージング ブロックです。|  
|[release](#release)|以前に成功したメッセージの予約を解放します。|  
|[release_ref](#release_ref)|この参照カウントを解放`multiple_join`メッセージング ブロックです。|  
|[reserve](#reserve)|これによって以前に提供メッセージを予約`multitype_join`メッセージング ブロックです。|  
|[unlink_target](#unlink_target)|ターゲット ブロックをこれからのリンクを解除`multitype_join`メッセージング ブロックです。|  
|[unlink_targets](#unlink_targets)|これからすべてのターゲットのリンクを解除`multitype_join`メッセージング ブロックです。 (上書き[isource::unlink_targets](isource-class.md#unlink_targets))。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ISource](isource-class.md)  
  
 `multitype_join`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="accept"></a> そのまま使用します。 

 これによって提供されたメッセージを受け入れる`multitype_join`ブロック、呼び出し元に所有権を転送します。  
  
```  
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`accept`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 呼び出し元は、現在の所有権を持つメッセージへのポインター。  
  
##  <a name="acquire_ref"></a> acquire_ref 

 この参照カウントを獲得`multitype_join`メッセージング ブロックを削除されないようにします。  
  
```  
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出すターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`中にこのソースにリンクされているオブジェクト、`link_target`メソッドです。  
  
##  <a name="consume"></a> 使用します。 

 によって以前に提供メッセージを使用して、`multitype_join`ブロックのメッセージングおよび呼び出し元に所有権を転送する、ターゲットが正常に予約されています。  
  
```  
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、予約済みの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`consume`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 ポインター、`message`呼び出し元がの所有権をオブジェクトします。  
  
### <a name="remarks"></a>コメント  
 `consume`メソッドは`accept`への呼び出しでは前に必ず必要がありますが、`reserve`返さ`true`です。  
  
##  <a name="link_target"></a> link_target 

 これをターゲット ブロックをリンク`multitype_join`メッセージング ブロックです。  
  
```  
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`ブロックをこのリンクを`multitype_join`メッセージング ブロックです。  
  
##  <a name="ctor"></a> multitype_join 

 `multitype_join` メッセージング ブロックを構築します。  
  
```  
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
 `_Tuple`  
 この `tuple` メッセージング ブロックのソースの `multitype_join` です。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
 `_Join`  
 コピー元の `multitype_join` メッセージング ブロックです。 元のオブジェクトが孤立しており、これが移動コンストラクターになることに注意してください。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 移動の構築はロックの状況では行われません。ということは、移動時に処理中の軽量タスクがないことを確認するのはユーザーの責任です。 そうしないと、例外または不整合な状態で、多数の競合が発生します。  
  
##  <a name="dtor"></a> ~multitype_join 

 破棄、`multitype_join`メッセージング ブロックです。  
  
```  
~multitype_join();
```  
  
##  <a name="release"></a> リリース 

 以前に成功したメッセージの予約を解放します。  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`release`メソッドです。  
  
##  <a name="release_ref"></a> release_ref 

 この参照カウントを解放`multiple_join`メッセージング ブロックです。  
  
```  
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出すターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`このソースからリンクが解除されるオブジェクト。 ソース ブロックがターゲット ブロック用に予約されたリソースを解放する許可されます。  
  
##  <a name="reserve"></a> 予約 

 これによって以前に提供メッセージを予約`multitype_join`メッセージング ブロックです。  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`オブジェクトの中に予約されています。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`reserve`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 `true` 場合は、メッセージが正常に予約された、`false`それ以外の場合。 予約は、さまざまな理由で失敗することが: メッセージが既に予約か、またはソースでした、予約を拒否するなど、別のターゲットで受け入れられます。  
  
### <a name="remarks"></a>コメント  
 呼び出した後`reserve`、成功した場合、いずれかを呼び出す必要があります`consume`または`release`かかるまたは所有している、メッセージをそれぞれ付与するためにします。  
  
##  <a name="unlink_target"></a> unlink_target 

 ターゲット ブロックをこれからのリンクを解除`multitype_join`メッセージング ブロックです。  
  
```  
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`このリンクを解除するブロック`multitype_join`メッセージング ブロックです。  
  
##  <a name="unlink_targets"></a> unlink_targets 

 これからすべてのターゲットのリンクを解除`multitype_join`メッセージング ブロックです。  
  
```  
virtual void unlink_targets();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [choice クラス](choice-class.md)   
 [join クラス](join-class.md)
