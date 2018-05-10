---
title: choice クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 56b936e1ecb3864b7a7bb95f3e552c16d2ce81d0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
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
 `T`  
 A `tuple`-した入力ソースのペイロードを表す型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`type`|型の別名`T`です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[選択肢](#ctor)|オーバーロードされます。 `choice` メッセージング ブロックを構築します。|  
|[~ choice デストラクター](#dtor)|破棄、`choice`メッセージング ブロックです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept](#accept)|これによって提供されたメッセージを受け入れる`choice`ブロック、呼び出し元に所有権を転送します。|  
|[acquire_ref](#acquire_ref)|この参照カウントを獲得`choice`メッセージング ブロックを削除されないようにします。|  
|[使用します。](#consume)|これによって以前に提供メッセージを使用して`choice`ブロックのメッセージングおよび呼び出し元に所有権を転送する、ターゲットが正常に予約されています。|  
|[has_value](#has_value)|チェックするかどうかこの`choice`メッセージング ブロックはまだ初期化されて、値を使用します。|  
|[index](#index)|インデックスを返します、`tuple`によって選択された要素を表す、`choice`メッセージング ブロックです。|  
|[link_target](#link_target)|これをターゲット ブロックをリンク`choice`メッセージング ブロックです。|  
|[release](#release)|以前に成功したメッセージの予約を解放します。|  
|[release_ref](#release_ref)|この参照カウントを解放`choice`メッセージング ブロックです。|  
|[reserve](#reserve)|これによって以前に提供メッセージを予約`choice`メッセージング ブロックです。|  
|[unlink_target](#unlink_target)|ターゲット ブロックをこれからのリンクを解除`choice`メッセージング ブロックです。|  
|[unlink_targets](#unlink_targets)|これからすべてのターゲットのリンクを解除`choice`メッセージング ブロックです。 (上書き[isource::unlink_targets](isource-class.md#unlink_targets))。|  
|[value](#value)|によって選択されたインデックスを持つメッセージを取得、`choice`メッセージング ブロックです。|  
  
## <a name="remarks"></a>コメント  
 Choice ブロックにより、受信メッセージの 1 つだけが使用されます。  
  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
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
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`accept`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 呼び出し元は、現在の所有権を持つメッセージへのポインター。  
  
##  <a name="acquire_ref"></a> acquire_ref 

 この参照カウントを獲得`choice`メッセージング ブロックを削除されないようにします。  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出すターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`中にこのソースにリンクされているオブジェクト、`link_target`メソッドです。  
  
##  <a name="ctor"></a> 選択肢 

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
 `_Tuple`  
 選択肢のソースの `tuple` です。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
 `_Choice`  
 コピー元の `choice` メッセージング ブロックです。 元のオブジェクトが孤立しており、これが移動コンストラクターになることに注意してください。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 移動の構築はロックの状況では行われません。ということは、移動時に処理中の軽量タスクがないことを確認するのはユーザーの責任です。 そうしないと、例外または不整合な状態で、多数の競合が発生します。  
  
##  <a name="dtor"></a> ~ 選択肢 

 破棄、`choice`メッセージング ブロックです。  
  
```  
~choice();
```  
  
##  <a name="consume"></a> 使用します。 

 これによって以前に提供メッセージを使用して`choice`ブロックのメッセージングおよび呼び出し元に所有権を転送する、ターゲットが正常に予約されています。  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
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
  
##  <a name="has_value"></a> has_value 

 チェックするかどうかこの`choice`メッセージング ブロックはまだ初期化されて、値を使用します。  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>戻り値  
 `true` ブロックは、値を受け取っている場合`false`それ以外の場合。  
  
##  <a name="index"></a> インデックス 

 インデックスを返します、`tuple`によって選択された要素を表す、`choice`メッセージング ブロックです。  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>戻り値  
 メッセージのインデックス。  
  
### <a name="remarks"></a>コメント  
 使用して、メッセージ ペイロードを抽出することができます、`get`メソッドです。  
  
##  <a name="link_target"></a> link_target 

 これをターゲット ブロックをリンク`choice`メッセージング ブロックです。  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`ブロックをこのリンクを`choice`メッセージング ブロックです。  
  
##  <a name="release"></a> リリース 

 以前に成功したメッセージの予約を解放します。  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity`の`message`リリースされているオブジェクトします。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`release`メソッドです。  
  
##  <a name="release_ref"></a> release_ref 

 この参照カウントを解放`choice`メッセージング ブロックです。  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出すターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`このソースからリンクが解除されるオブジェクト。 ソース ブロックがターゲット ブロック用に予約されたリソースを解放する許可されます。  
  
##  <a name="reserve"></a> 予約 

 これによって以前に提供メッセージを予約`choice`メッセージング ブロックです。  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
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

 ターゲット ブロックをこれからのリンクを解除`choice`メッセージング ブロックです。  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 ポインター、`ITarget`このリンクを解除するブロック`choice`メッセージング ブロックです。  
  
##  <a name="unlink_targets"></a> unlink_targets 

 これからすべてのターゲットのリンクを解除`choice`メッセージング ブロックです。  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドがあるため、デストラクターから呼び出される必要はありませんは、内部デストラクター`single_assignment`ブロックが正常に解除されます。  
  
##  <a name="value"></a> 値 

 によって選択されたインデックスを持つメッセージを取得、`choice`メッセージング ブロックです。  
  
```  
template <
    typename _Payload_type  
>  
_Payload_type const& value();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Payload_type`  
 メッセージ ペイロードの型。  
  
### <a name="return-value"></a>戻り値  
 メッセージのペイロード。  
  
### <a name="remarks"></a>コメント  
 `choice`メッセージング ブロックは、さまざまなペイロードの種類の入力を行うことができます、取得時点で、ペイロードの種類を指定する必要があります。 結果に基づいて、種類を指定できます、`index`メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [クラスを結合します。](join-class.md)   
 [single_assignment クラス](single-assignment-class.md)
