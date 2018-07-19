---
title: IExecutionContext 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IExecutionContext
- CONCRTRM/concurrency::IExecutionContext
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::Dispatch
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetId
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetProxy
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::GetScheduler
- CONCRTRM/concurrency::IExecutionContext::IExecutionContext::SetProxy
dev_langs:
- C++
helpviewer_keywords:
- IExecutionContext structure
ms.assetid: f3108089-ecda-4b07-86db-3efae60c31e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c194dc7ecd4af0092dd304b17a8230cda6a8598
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692900"
---
# <a name="iexecutioncontext-structure"></a>IExecutionContext 構造体
特定の仮想プロセッサで実行でき、協調的にコンテキストを切り替えることができる実行コンテキストへのインターフェイスです。  
  
## <a name="syntax"></a>構文  
  
```
struct IExecutionContext;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IExecutionContext::Dispatch](#dispatch)|スレッド プロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 これは、スケジューラのメイン ワーカー ルーチンでなければなりません。|  
|[IExecutionContext::GetId](#getid)|実行コンテキストの一意の識別子を返します。|  
|[IExecutionContext::GetProxy](#getproxy)|このコンテキストを実行しているスレッド プロキシへのインターフェイスを返します。|  
|[IExecutionContext::GetScheduler](#getscheduler)|この実行コンテキストが属するスケジューラへのインターフェイスを返します。|  
|[IExecutionContext::SetProxy](#setproxy)|スレッド プロキシをこの実行コンテキストに関連付けます。 コンテキストの実行を開始する前に、関連付けられたスレッド プロキシがこのメソッドの権限を呼び出す`Dispatch`メソッドです。|  
  
## <a name="remarks"></a>コメント  
 カスタム スケジューラを同時実行ランタイムのリソース マネージャーとのインターフェイスを実装している場合は、実装する必要があります、`IExecutionContext`インターフェイスです。 リソース マネージャーによって作成されたスレッドが実行することにより、スケジューラの代わりの作業を実行、`IExecutionContext::Dispatch`メソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IExecutionContext`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="dispatch"></a>  Iexecutioncontext::dispatch メソッド  
 スレッド プロキシが特定の実行コンテキストの実行を開始するときに呼び出されるメソッド。 これは、スケジューラのメイン ワーカー ルーチンでなければなりません。  
  
```
virtual void Dispatch(_Inout_ DispatchState* pDispatchState) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pDispatchState`  
 この実行コンテキストがディスパッチされる状態へのポインター。 ディスパッチ状態の詳細については、次を参照してください。 [DispatchState](dispatchstate-structure.md)です。  
  
##  <a name="getid"></a>  Iexecutioncontext::getid メソッド  
 実行コンテキストの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 一意の整数識別子。  
  
### <a name="remarks"></a>コメント  
 メソッドを使用する必要があります`GetExecutionContextId`を実装するオブジェクトの一意の識別子を取得する、`IExecutionContext`インターフェイス、メソッドのパラメーターとしてインターフェイスを使用する前に、リソース マネージャーでを指定します。 同じ識別子を返している必要がときに、`GetId`関数が呼び出されます。  
  
 未定義の動作は、別のソースから取得した識別子の可能性があります。  
  
##  <a name="getproxy"></a>  Iexecutioncontext::getproxy メソッド  
 このコンテキストを実行しているスレッド プロキシへのインターフェイスを返します。  
  
```
virtual IThreadProxy* GetProxy() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 `IThreadProxy` インターフェイス。 呼び出して、実行コンテキストのスレッド プロキシが初期化されていない場合`SetProxy`、関数が返す必要があります`NULL`です。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーを呼び出す、`SetProxy`実行コンテキストでは、上のメソッドで、`IThreadProxy`インターフェイスを入力する前に、パラメーターとして、`Dispatch`メソッドをコンテキストでします。 この引数を格納してへの呼び出しで返す必要が`GetProxy()`です。  
  
##  <a name="getscheduler"></a>  Iexecutioncontext::getscheduler メソッド  
 この実行コンテキストが属するスケジューラへのインターフェイスを返します。  
  
```
virtual IScheduler* GetScheduler() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 `IScheduler` インターフェイス。  
  
### <a name="remarks"></a>コメント  
 有効な実行コンテキストを初期化するために必要な`IScheduler`インターフェイス メソッドのパラメーターとして使用する前に、リソース マネージャーでを指定します。  
  
##  <a name="setproxy"></a>  Iexecutioncontext::setproxy メソッド  
 スレッド プロキシをこの実行コンテキストに関連付けます。 コンテキストの実行を開始する前に、関連付けられたスレッド プロキシがこのメソッドの権限を呼び出す`Dispatch`メソッドです。  
  
```
virtual void SetProxy(_Inout_ IThreadProxy* pThreadProxy) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pThreadProxy`  
 入力されるスレッド プロキシへのインターフェイス、`Dispatch`メソッドをこの実行コンテキスト。  
  
### <a name="remarks"></a>コメント  
 パラメーターを保存することが求め`pThreadProxy`への呼び出しで返すと、`GetProxy`メソッドです。 リソース マネージャーは、実行コンテキストに関連付けられているスレッド プロキシは、スレッド プロキシが実行中に変更しないという、`Dispatch`メソッドです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IScheduler 構造体](ischeduler-structure.md)   
 [IThreadProxy 構造体](ithreadproxy-structure.md)
