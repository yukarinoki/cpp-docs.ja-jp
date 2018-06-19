---
title: IExecutionResource 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
dev_langs:
- C++
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc69c30f30d25179427ee8e59c536bb7cb5b483d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692130"
---
# <a name="iexecutionresource-structure"></a>IExecutionResource 構造体
ハードウェア スレッドの抽象化です。  
  
## <a name="syntax"></a>構文  
  
```
struct IExecutionResource;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IExecutionResource::CurrentSubscriptionLevel](#currentsubscriptionlevel)|ルートの数とこの実行リソースが表す基になるハードウェア スレッドに関連付けられている外部のスレッドをサブスクライブしているアクティブ化された仮想プロセッサの数を返します。|  
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|この実行リソースを表すハードウェア スレッドの一意の識別子を返します。|  
|[IExecutionResource::GetNodeId](#getnodeid)|この実行リソースが属するプロセッサ ノードの一意の識別子を返します。|  
|[IExecutionResource::Remove](#remove)|この実行リソースをリソース マネージャーを返します。|  
  
## <a name="remarks"></a>コメント  
 実行リソースはスタンドアロンでか仮想プロセッサ ルートに関連付けられています。 アプリケーションのスレッドが、スレッドのサブスクリプションを作成するときは、スタンドアロンの実行リソースが作成されます。 メソッド[ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread)と[ischedulerproxy::requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)スレッドのサブスクリプションを作成して返す、`IExecutionResource`インターフェイスを表す、サブスクリプション。 スレッドのサブスクリプションを作成すると、特定のスレッドが作業に参加するリソース マネージャーに通知する方法は、スケジューラにリソース マネージャーを割り当てます仮想プロセッサ ルートと、スケジューラ キューに置かれたです。 リソース マネージャーは、できるハードウェア スレッドの規定量を超えるを避けるために情報を使用します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IExecutionResource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="currentsubscriptionlevel"></a>  Iexecutionresource::currentsubscriptionlevel メソッド  
 ルートの数とこの実行リソースが表す基になるハードウェア スレッドに関連付けられている外部のスレッドをサブスクライブしているアクティブ化された仮想プロセッサの数を返します。  
  
```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 現在のサブスクリプション レベル。  
  
### <a name="remarks"></a>コメント  
 サブスクリプション レベルは、実行中のスレッドの数が、ハードウェア スレッドに関連付けを示しています。 これには、リソース マネージャーは、サブスクライブしているスレッドとに、スレッド プロキシを実行している仮想プロセッサ ルートの形式での対応するスレッドにはのみが含まれます。  
  
 メソッドを呼び出す[ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread)、またはメソッドの[ischedulerproxy::requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)パラメーターを使用して`doSubscribeCurrentThread`値に設定`true`を 1 つのハードウェア スレッドのサブスクリプション レベルを増やします。 返すことも、`IExecutionResource`サブスクリプションを表すインターフェイス。 対応する呼び出し、 [iexecutionresource::remove](#remove)デクリメント ハードウェア スレッドのサブスクリプション レベルで 1 つです。  
  
 メソッドを使用して仮想プロセッサ ルートをアクティブ化する[ivirtualprocessorroot::activate](ivirtualprocessorroot-structure.md#activate)を 1 つのハードウェア スレッドのサブスクリプション レベルを増やします。 メソッド[ivirtualprocessorroot::deactivate](ivirtualprocessorroot-structure.md#deactivate)、または[iexecutionresource::remove](#remove)サブスクリプション レベルをアクティブ化された仮想プロセッサ ルートで呼び出されたときに 1 つだけデクリメントします。  
  
 リソース マネージャーは、スケジューラ間でリソースを移動するかを判断するための方法の 1 つとして、サブスクリプション レベルの情報を使用します。  
  
##  <a name="getexecutionresourceid"></a>  Iexecutionresource::getexecutionresourceid メソッド  
 この実行リソースを表すハードウェア スレッドの一意の識別子を返します。  
  
```
virtual unsigned int GetExecutionResourceId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 この実行リソースを基になるハードウェア スレッドの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 各ハードウェア スレッドには、同時実行ランタイムによって一意の識別子が割り当てられます。 複数の実行リソースが関連付けられているハードウェアの場合、スレッドがすべて必要である同じ実行リソース識別子。  
  
##  <a name="getnodeid"></a>  Iexecutionresource::getnodeid メソッド  
 この実行リソースが属するプロセッサ ノードの一意の識別子を返します。  
  
```
virtual unsigned int GetNodeId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 プロセッサのノードの一意の識別子。  
  
### <a name="remarks"></a>コメント  
 同時実行ランタイムでは、プロセッサのノードのグループでは、システム上のハードウェア スレッドを表します。 通常、ノードは、システムのハードウェア トポロジから派生します。 たとえば、特定のソケットまたは特定の NUMA ノード上のすべてのプロセッサが同一プロセッサ ノードに属している可能性があります。 リソース マネージャーは、以降でこれらのノードに一意の識別子を割り当てます`0`含む`nodeCount - 1`ここで、`nodeCount`システム上のノードのプロセッサの合計数を表します。  
  
 ノードの数は、関数から取得できる[GetProcessorNodeCount](concurrency-namespace-functions.md)です。  
  
##  <a name="remove"></a>  Iexecutionresource::remove メソッド  
 この実行リソースをリソース マネージャーを返します。  
  
```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pScheduler`  
 この実行リソースを削除する要求を行っているスケジューラへのインターフェイス。  
  
### <a name="remarks"></a>コメント  
 このメソッドを使用して、スタンドアロンの実行リソースと同様に仮想プロセッサ ルート リソース マネージャーに関連付けられている実行リソースを返します。  
  
 メソッドのいずれかから受信した場合、これは、スタンドアロンの実行リソース[ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread)または[ischedulerproxy::requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)を呼び出す、メソッド`Remove`にリソースが作成されたスレッドのサブスクリプションが終了を表します。 スケジューラのプロキシをシャット ダウンする前にすべてのスレッドのサブスクリプションを終了するために必要なして呼び出す必要があります`Remove`サブスクリプションを作成したスレッドからです。  
  
 仮想プロセッサ ルートすぎる、返されるリソース マネージャーを呼び出すことによって、`Remove`メソッド、ため、インターフェイス`IVirtualProcessorRoot`から継承、`IExecutionResource`インターフェイスです。 呼び出しに応答するか、仮想プロセッサ ルートを返す必要があります、 [ischeduler::removevirtualprocessors](ischeduler-structure.md#removevirtualprocessors)メソッドから取得したオーバーサブスク ライブの仮想プロセッサ ルートが完了したときや、 [Ischedulerproxy::createoversubscriber](ischedulerproxy-structure.md#createoversubscriber)メソッドです。 仮想プロセッサ ルートについての制限がないスレッドを呼び出すことができます、`Remove`メソッドです。  
  
 `invalid_argument` スローされる場合、パラメーター`pScheduler`に設定されている`NULL`です。  
  
 `invalid_operation` スローされる場合、パラメーター`pScheduler`現在のスレッドがスレッドのサブスクリプションを作成したスレッドと異なる場合は、スケジューラ、または、スタンドアロンの実行リソースでは、この実行リソースが作成されたことを異なる。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)
