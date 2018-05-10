---
title: message_processor クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
dev_langs:
- C++
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 95e95cc84ca999402e0d64c0699750bb92203cef
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="messageprocessor-class"></a>message_processor クラス
`message_processor` クラスは、`message` オブジェクトを処理するための抽象基底クラスです。 メッセージの順序は保証されません。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class message_processor;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージ内のペイロードのデータ型は、これによって処理される`message_processor`オブジェクト。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`type`|型の別名`T`です。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[async_send](#async_send)|派生クラスでオーバーライドされると、ときに、非同期的にブロックにメッセージを配置します。|  
|[sync_send](#sync_send)|派生クラスでオーバーライドされると、ときに、同期的にブロックにメッセージを配置します。|  
|[wait](#wait)|派生クラスでオーバーライドされると、すべての非同期操作の完了を待機します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|派生クラスでオーバーライドされると、ブロックにメッセージの転送処理を実行します。 新しいメッセージが追加され、キューが空にすることが検出するたびに 1 回呼び出されます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `message_processor`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="async_send"></a> async_send 

 派生クラスでオーバーライドされると、ときに、非同期的にブロックにメッセージを配置します。  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 A`message`非同期的に送信するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 プロセッサの実装では、このメソッドをオーバーライドする必要があります。  
  
##  <a name="process_incoming_message"></a> process_incoming_message 

 派生クラスでオーバーライドされると、ブロックにメッセージの転送処理を実行します。 新しいメッセージが追加され、キューが空にすることが検出するたびに 1 回呼び出されます。  
  
```
virtual void process_incoming_message() = 0;
```  
  
### <a name="remarks"></a>コメント  
 メッセージ ブロックの実装では、このメソッドをオーバーライドする必要があります。  
  
##  <a name="sync_send"></a> sync_send 

 派生クラスでオーバーライドされると、ときに、同期的にブロックにメッセージを配置します。  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Msg`  
 A`message`同期的に送信するオブジェクト。  
  
### <a name="remarks"></a>コメント  
 プロセッサの実装では、このメソッドをオーバーライドする必要があります。  
  
##  <a name="wait"></a> 待機 

 派生クラスでオーバーライドされると、すべての非同期操作の完了を待機します。  
  
```
virtual void wait() = 0;
```  
  
### <a name="remarks"></a>コメント  
 プロセッサの実装では、このメソッドをオーバーライドする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [ordered_message_processor クラス](ordered-message-processor-class.md)
