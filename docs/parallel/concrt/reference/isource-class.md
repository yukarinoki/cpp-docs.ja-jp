---
title: ISource クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
dev_langs:
- C++
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 27b1aa57a8c90c2f996aab3b8ee47797f15edd5b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="isource-class"></a>ISource クラス
`ISource` クラスは、すべてのソース ブロック用のインターフェイスです。 ソース ブロックは、メッセージを `ITarget` ブロックに伝達します。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class ISource;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージ内のペイロードのデータ型は、ソース ブロックによって生成されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`source_type`|型の別名`T`です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[~ ISource デストラクター](#dtor)|`ISource` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[accept](#accept)|派生クラスでオーバーライドされると、これによって提供されたメッセージを受け入れる`ISource`ブロック、呼び出し元に所有権を転送します。|  
|[acquire_ref](#acquire_ref)|派生クラスでオーバーライドされると、この参照カウントを獲得`ISource`ブロックを削除されないようにします。|  
|[使用します。](#consume)|派生クラスでオーバーライドされると、これによって以前に提供メッセージを使用して`ISource`をブロックし、呼び出し元に所有権を転送する、ターゲットが正常に予約されています。|  
|[link_target](#link_target)|派生クラスでオーバーライドされると、これをターゲット ブロックをリンク`ISource`ブロックします。|  
|[release](#release)|派生クラスでオーバーライドされると、以前に成功したメッセージの予約を解放します。|  
|[release_ref](#release_ref)|派生クラスでオーバーライドされると、この参照カウントを解放`ISource`ブロックします。|  
|[reserve](#reserve)|派生クラスでオーバーライドされると、これによって以前に提供メッセージを予約`ISource`ブロックします。|  
|[unlink_target](#unlink_target)|派生クラスでオーバーライドされると、ターゲット ブロックをこれからのリンクを解除`ISource`場合、ブロックをリンクできる以前が見つかりました。|  
|[unlink_targets](#unlink_targets)|派生クラスでオーバーライドされると、これからすべてのターゲット ブロックのリンクを解除`ISource`ブロックします。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ISource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="accept"></a> そのまま使用します。 

 派生クラスでオーバーライドされると、これによって提供されたメッセージを受け入れる`ISource`ブロック、呼び出し元に所有権を転送します。  
  
```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`accept`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 呼び出し元は、現在の所有権を持つメッセージへのポインター。  
  
### <a name="remarks"></a>コメント  
 `accept`メソッドは、メッセージは、これによって提供されているときに、ターゲットによって呼び出されます。`ISource`ブロックします。 返されるメッセージ ポインターに渡されたものと異なる場合があります、`propagate`のメソッド、`ITarget`メッセージのコピーを作成する場合はこのソースをブロックします。  
  
##  <a name="acquire_ref"></a> acquire_ref 

 派生クラスでオーバーライドされると、この参照カウントを獲得`ISource`ブロックを削除されないようにします。  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出すターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`中にこのソースにリンクされているオブジェクト、`link_target`メソッドです。  
  
##  <a name="consume"></a> 使用します。 

 派生クラスでオーバーライドされると、これによって以前に提供メッセージを使用して`ISource`をブロックし、呼び出し元に所有権を転送する、ターゲットが正常に予約されています。  
  
```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
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
  
##  <a name="dtor"></a> ~ ISource 

 `ISource` オブジェクトを破棄します。  
  
```
virtual ~ISource();
```  
  
##  <a name="link_target"></a> link_target 

 派生クラスでオーバーライドされると、これをターゲット ブロックをリンク`ISource`ブロックします。  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 これにリンクされているターゲット ブロックへのポインター`ISource`ブロックします。  
  
##  <a name="release"></a> リリース 

 派生クラスでオーバーライドされると、以前に成功したメッセージの予約を解放します。  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、予約済みの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`release`メソッドです。  
  
##  <a name="release_ref"></a> release_ref 

 派生クラスでオーバーライドされると、この参照カウントを解放`ISource`ブロックします。  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 このメソッドを呼び出すターゲット ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、`ITarget`このソースからリンクが解除されるオブジェクト。 ソース ブロックがターゲット ブロック用に予約されたリソースを解放する許可されます。  
  
##  <a name="reserve"></a> 予約 

 派生クラスでオーバーライドされると、これによって以前に提供メッセージを予約`ISource`ブロックします。  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_MsgId`  
 `runtime_object_identity` 、提供されているの`message`オブジェクト。  
  
 `_PTarget`  
 呼び出しているターゲット ブロックへのポインター、`reserve`メソッドです。  
  
### <a name="return-value"></a>戻り値  
 `true` 場合は、メッセージが正常に予約された、`false`それ以外の場合。 予約は、さまざまな理由で失敗することが: メッセージが既に予約か、またはソースでした、予約を拒否するなど、別のターゲットで受け入れられます。  
  
### <a name="remarks"></a>コメント  
 呼び出した後`reserve`、成功した場合、いずれかを呼び出す必要があります`consume`または`release`かかるまたは所有している、メッセージをそれぞれ付与するためにします。  
  
##  <a name="unlink_target"></a> unlink_target 

 派生クラスでオーバーライドされると、ターゲット ブロックをこれからのリンクを解除`ISource`場合、ブロックをリンクできる以前が見つかりました。  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_PTarget`  
 これからのリンクが解除されているターゲット ブロックへのポインター`ISource`ブロックします。  
  
##  <a name="unlink_targets"></a> unlink_targets 

 派生クラスでオーバーライドされると、これからすべてのターゲット ブロックのリンクを解除`ISource`ブロックします。  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ITarget クラス](itarget-class.md)
