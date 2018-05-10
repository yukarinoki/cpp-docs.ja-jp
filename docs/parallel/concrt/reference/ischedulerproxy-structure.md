---
title: ISchedulerProxy 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
dev_langs:
- C++
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 65198998666391763ef32a55cd12e86529e619ed
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy 構造体
スケジューラは、このインターフェイスを使用して同時実行ランタイムのリソース マネージャーと通信して、リソース割り当てをネゴシエートします。  
  
## <a name="syntax"></a>構文  
  
```
struct ISchedulerProxy;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ISchedulerProxy::BindContext](#bindcontext)|いずれかで関連付けられていない場合は、スレッド プロキシを実行コンテキストを関連付けます。|  
|[ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|既存の実行リソースに関連付けられているハードウェア スレッドで新しい仮想プロセッサ ルートを作成します。|  
|[ISchedulerProxy::RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|仮想プロセッサ ルートの最初の割り当てを要求します。 すべての仮想プロセッサ ルートでは、スケジューラの作業を実行できる 1 つのスレッドを実行する機能を表します。|  
|[ISchedulerProxy::Shutdown](#shutdown)|スケジューラがシャット ダウンしているリソース マネージャーに通知します。 これは、結果、リソース マネージャーは、スケジューラに付与されたすべてのリソースを直ちに解放します。|  
|[ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|このスケジューラに関連付けることが、リソース マネージャーで、現在のスレッドを登録します。|  
|[ISchedulerProxy::UnbindContext](#unbindcontext)|指定された実行コンテキストからスレッド プロキシの関連付けを解除、`pContext`パラメーターとし、スレッド プロキシ工場出荷時の空きプールに返します。 このメソッドを使用してバインドされた実行コンテキストでのみ呼び出すことがあります、 [ischedulerproxy::bindcontext](#bindcontext)メソッドを介してされて開始されていないと、`pContext`のパラメーター、 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)メソッドの呼び出しです。|  
  
## <a name="remarks"></a>コメント  
 リソース マネージャーに渡します、`ISchedulerProxy`インターフェイスを使用して登録するすべてのスケジューラを[iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler)メソッドです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ISchedulerProxy`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="bindcontext"></a>  Ischedulerproxy::bindcontext メソッド  
 いずれかで関連付けられていない場合は、スレッド プロキシを実行コンテキストを関連付けます。  
  
```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 実行コンテキストに関連付けるスレッド プロキシへのインターフェイス。  
  
### <a name="remarks"></a>コメント  
 通常、 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)メソッドでは、スレッド プロキシは要求時に実行コンテキストにバインドします。 ある、ただし、いることを確認するには、事前にコンテキストをバインドする必要がある状況、`SwitchTo`メソッドが既にバインドされているコンテキストに切り替えます。 これはスケジュール コンテキスト、メモリを割り当てメソッドを呼び出すことはできません UMS の場合であり、スレッド プロキシをバインドする必要がありますメモリの割り当てスレッド プロキシ工場出荷時の空きプールでは、スレッド プロキシが用意できていない場合。  
  
 `invalid_argument` スローされる場合、パラメーター`pContext`プロパティ値を持つ`NULL`します。  
  
##  <a name="createoversubscriber"></a>  Ischedulerproxy::createoversubscriber メソッド  
 既存の実行リソースに関連付けられているハードウェア スレッドで新しい仮想プロセッサ ルートを作成します。  
  
```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pExecutionResource`  
 `IExecutionResource`オーバーサブスク ライブするハードウェア スレッドを表すインターフェイスです。  
  
### <a name="return-value"></a>戻り値  
 `IVirtualProcessorRoot` インターフェイス。  
  
### <a name="remarks"></a>コメント  
 スケジューラが一定期間の特定のハードウェア スレッドをオーバーサブスク ライブたい場合に、このメソッドを使用します。 仮想プロセッサ ルートで完了したら、する必要がありますに戻す、リソース マネージャーを呼び出して、[削除](iexecutionresource-structure.md#remove)メソッドを`IVirtualProcessorRoot`インターフェイスです。  
  
 でもオーバーサブスク ライブできます既存の仮想プロセッサ ルートであるため、`IVirtualProcessorRoot`インターフェイスから継承、`IExecutionResource`インターフェイスです。  
  
##  <a name="requestinitialvirtualprocessors"></a>  Ischedulerproxy::requestinitialvirtualprocessors メソッド  
 仮想プロセッサ ルートの最初の割り当てを要求します。 すべての仮想プロセッサ ルートでは、スケジューラの作業を実行できる 1 つのスレッドを実行する機能を表します。  
  
```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `doSubscribeCurrentThread`  
 現在のスレッドをサブスクライブし、リソースの割り当て時に考慮するかどうか。  
  
### <a name="return-value"></a>戻り値  
 `IExecutionResource`場合に、現在のスレッド、インターフェイス、パラメーター`doSubscribeCurrentThread`プロパティ値を持つ`true`します。 値が場合`false`、メソッドを返します`NULL`です。  
  
### <a name="remarks"></a>コメント  
 スケジューラは作業を実行する前に、リソース マネージャーから仮想プロセッサ ルートを要求するのにこのメソッドを使用してください。 リソース マネージャーは、スケジューラのポリシーへのアクセスを使用して[ischeduler::getpolicy](ischeduler-structure.md#getpolicy)ポリシー キーの値を使用して`MinConcurrency`、`MaxConcurrency`と`TargetOversubscriptionFactor`に割り当てるハードウェア スレッドの数を決定する、スケジューラ最初に、すべてのハードウェア スレッドを作成する方法の多くの仮想プロセッサ ルート。 スケジューラ ポリシーを使用して、スケジューラの初期の割り当てを決定する方法の詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)です。  
  
 リソース マネージャーは、メソッドを呼び出すことによってスケジューラにリソースを付与[ischeduler::addvirtualprocessors](ischeduler-structure.md#addvirtualprocessors)仮想プロセッサ ルートのリストを使用します。 このメソッドはコールバックとして、スケジューラにこのメソッドが戻る前にします。  
  
 スケジューラがパラメーターを設定して、現在のスレッドのサブスクリプションを要求したかどうか`doSubscribeCurrentThread`に`true`、メソッドを返します、`IExecutionResource`インターフェイスです。 使用して、後で、サブスクリプションを終了する必要があります、 [iexecutionresource::remove](iexecutionresource-structure.md#remove)メソッドです。  
  
 ハードウェア スレッドが選択されているかを決定するときに、リソース マネージャーはプロセッサ ノード アフィニティを最適化しようとします。 サブスクリプションが現在のスレッドの要求された場合は、現在のスレッドがこのスケジューラに割り当てられている作業に参加することを示します。 このような場合は、割り当てられた仮想プロセッサ ルートは、現在のスレッドが、可能であれば実行しているプロセッサのノードに配置されます。  
  
 スレッドのサブスクライブの動作は、基になるハードウェア スレッドのサブスクリプション レベルを 1 つずつ増加します。 サブスクリプションが終了した場合に、いずれかによって、サブスクリプション レベルが減少します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)です。  
  
##  <a name="shutdown"></a>  Ischedulerproxy::shutdown メソッド  
 スケジューラがシャット ダウンしているリソース マネージャーに通知します。 これは、結果、リソース マネージャーは、スケジューラに付与されたすべてのリソースを直ちに解放します。  
  
```
virtual void Shutdown() = 0;
```  
  
### <a name="remarks"></a>コメント  
 すべて`IExecutionContext`インターフェイスのメソッドを使用して、外部スレッドをサブスクライブした結果として受信したスケジューラ`ISchedulerProxy::RequestInitialVirtualProcessors`または`ISchedulerProxy::SubscribeCurrentThread`をリソース マネージャーを返す必要があるを使用して`IExecutionResource::Remove`スケジューラでは、それ自体をシャット ダウンする前にします。  
  
 非アクティブ化されたいずれかの仮想プロセッサ ルート、スケジューラがあった場合は、それらをアクティブ化する必要がありますを使用して[ivirtualprocessorroot::activate](ivirtualprocessorroot-structure.md#activate)のままにして実行スレッド プロキシがあると、`Dispatch`実行メソッド呼び出す前にディスパッチするコンテキスト`Shutdown`スケジューラ プロキシでします。  
  
 呼び出しによって付与リソース マネージャーを個別に返すすべての仮想プロセッサ ルートのスケジューラの必要はありません、`Remove`メソッドすべての仮想プロセッサ ルートはシャット ダウン時にリソース マネージャーに返されるためです。  
  
##  <a name="subscribecurrentthread"></a>  Ischedulerproxy::subscribecurrentthread メソッド  
 このスケジューラに関連付けることが、リソース マネージャーで、現在のスレッドを登録します。  
  
```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 `IExecutionResource`ランタイムの現在のスレッドを表すインターフェイスします。  
  
### <a name="remarks"></a>コメント  
 リソース マネージャーは、スケジューラ、およびその他のスケジューラにリソースを割り当てているときに、現在のスレッドを考慮する場合は、このメソッドを使用します。 作業に参加するスレッドのプランは、スケジューラを受け取るリソース マネージャーから仮想プロセッサ ルートと、スケジューラ キューに置かれたときに特に便利です。 リソース マネージャーは、システム上のハードウェア スレッドの不要なオーバー サブスクリプションを防ぐために情報を使用します。  
  
 リソース マネージャーにこのメソッドを使用して受信した実行リソースを返す必要があるを使用して、 [iexecutionresource::remove](iexecutionresource-structure.md#remove)メソッドです。 呼び出すスレッド、`Remove`メソッドは既に呼び出されている同じスレッドである必要があります、`SubscribeCurrentThread`メソッドです。  
  
 スレッドのサブスクライブの動作は、基になるハードウェア スレッドのサブスクリプション レベルを 1 つずつ増加します。 サブスクリプションが終了した場合に、いずれかによって、サブスクリプション レベルが減少します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)です。  
  
##  <a name="unbindcontext"></a>  Ischedulerproxy::unbindcontext メソッド  
 指定された実行コンテキストからスレッド プロキシの関連付けを解除、`pContext`パラメーターとし、スレッド プロキシ工場出荷時の空きプールに返します。 このメソッドを使用してバインドされた実行コンテキストでのみ呼び出すことがあります、 [ischedulerproxy::bindcontext](#bindcontext)メソッドを介してされて開始されていないと、`pContext`のパラメーター、 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)メソッドの呼び出しです。  
  
```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 スレッド プロキシとの関連付けを解除する実行コンテキスト。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IScheduler 構造体](ischeduler-structure.md)   
 [IThreadProxy 構造体](ithreadproxy-structure.md)   
 [IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)   
 [IResourceManager 構造体](iresourcemanager-structure.md)
