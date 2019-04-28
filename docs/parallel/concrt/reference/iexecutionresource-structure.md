---
title: IExecutionResource 構造体
ms.date: 11/04/2016
f1_keywords:
- IExecutionResource
- CONCRTRM/concurrency::IExecutionResource
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::CurrentSubscriptionLevel
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetExecutionResourceId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::GetNodeId
- CONCRTRM/concurrency::IExecutionResource::IExecutionResource::Remove
helpviewer_keywords:
- IExecutionResource structure
ms.assetid: 6b27042b-b98c-4f7f-b831-566950af84cd
ms.openlocfilehash: 9f8f5c5629e9794ca8ee2cc6bedbc4ba6bfdb24d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62262516"
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
|[IExecutionResource::CurrentSubscriptionLevel](#currentsubscriptionlevel)|ルートの数とこの実行リソースが表す基になるハードウェア スレッドに関連付けられている外部のスレッドを購読してアクティブ化された仮想プロセッサの数を返します。|
|[IExecutionResource::GetExecutionResourceId](#getexecutionresourceid)|この実行リソースを表すハードウェア スレッドの一意の識別子を返します。|
|[IExecutionResource::GetNodeId](#getnodeid)|この実行リソースが属するプロセッサ ノードの一意の識別子を返します。|
|[IExecutionResource::Remove](#remove)|この実行リソースをリソース マネージャーを返します。|

## <a name="remarks"></a>Remarks

実行リソースはスタンドアロンでまたは仮想プロセッサ ルートに関連付けられています。 アプリケーションのスレッドがスレッドのサブスクリプションを作成するときに、スタンドアロンの実行リソースが作成されます。 メソッド[ISchedulerProxy::SubscribeThread](ischedulerproxy-structure.md#subscribecurrentthread)と[ischedulerproxy::requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)スレッドのサブスクリプションを作成して返す、`IExecutionResource`インターフェイスを表す、サブスクリプション。 スレッドのサブスクリプションを作成すると、Resource Manager がスケジューラに割り当てる仮想プロセッサ ルートと、スケジューラのキューに置かれた、特定のスレッドが作業に参加する Resource Manager に通知する方法です。 リソース マネージャーは、可能なハードウェア スレッド オーバーサブスク ライブすることを回避するために、情報を使用します。

## <a name="inheritance-hierarchy"></a>継承階層

`IExecutionResource`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="currentsubscriptionlevel"></a>  Iexecutionresource::currentsubscriptionlevel メソッド

ルートの数とこの実行リソースが表す基になるハードウェア スレッドに関連付けられている外部のスレッドを購読してアクティブ化された仮想プロセッサの数を返します。

```
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>戻り値

現在のサブスクリプション レベル。

### <a name="remarks"></a>Remarks

サブスクリプション レベルは、実行中のスレッドの数はハードウェア スレッドに関連付けられたを指示します。 これには、リソース マネージャーは、サブスクライブしているスレッドとに、スレッド プロキシを実行している仮想プロセッサ ルートの形式での対応のスレッドにはのみが含まれます。

メソッドを呼び出す[ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread)、またはメソッド[ischedulerproxy::requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)パラメーターと共に`doSubscribeCurrentThread`値に設定**true**ハードウェア スレッドのサブスクリプション レベルを 1 ずつインクリメントします。 返すことも、`IExecutionResource`サブスクリプションを表すインターフェイス。 対応する呼び出し、 [iexecutionresource::remove](#remove)デクリメントを 1 つのハードウェア スレッドのサブスクリプション レベル。

メソッドを使用して仮想プロセッサ ルートをアクティブ化する[ivirtualprocessorroot::activate](ivirtualprocessorroot-structure.md#activate)ハードウェア スレッドのサブスクリプション レベルを 1 ずつインクリメントします。 メソッド[ivirtualprocessorroot::deactivate](ivirtualprocessorroot-structure.md#deactivate)、または[iexecutionresource::remove](#remove)を 1 つをアクティブ化された仮想プロセッサ ルートで呼び出されると、サブスクリプション レベルをデクリメントします。

Resource Manager は、スケジューラ間でリソースを移動するかを判断する方法の 1 つとして、サブスクリプション レベルの情報を使用します。

##  <a name="getexecutionresourceid"></a>  Iexecutionresource::getexecutionresourceid メソッド

この実行リソースを表すハードウェア スレッドの一意の識別子を返します。

```
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>戻り値

この実行リソースを基になるハードウェア スレッドの一意の識別子。

### <a name="remarks"></a>Remarks

各ハードウェア スレッドには、同時実行ランタイムによって一意の識別子が割り当てられます。 複数の実行リソースが関連付けられているハードウェアである場合、スレッドすべてが同じ実行リソース識別子。

##  <a name="getnodeid"></a>  Iexecutionresource::getnodeid メソッド

この実行リソースが属するプロセッサ ノードの一意の識別子を返します。

```
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>戻り値

プロセッサ ノードの一意の識別子。

### <a name="remarks"></a>Remarks

同時実行ランタイムでは、プロセッサのノードのグループで、システム上のハードウェア スレッドを表します。 ノードは、通常、システムのハードウェア トポロジから派生します。 たとえば、特定のソケットまたは特定の NUMA ノードのすべてのプロセッサが同一プロセッサ ノードに属している可能性があります。 Resource Manager では、以降ではこれらのノードに一意の識別子を割り当てます`0`まで`nodeCount - 1`ここで、`nodeCount`システム上のプロセッサ ノードの合計数を表します。

ノードの数は、関数から取得できます[GetProcessorNodeCount](concurrency-namespace-functions.md)します。

##  <a name="remove"></a>  Iexecutionresource::remove メソッド

この実行リソースをリソース マネージャーを返します。

```
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>パラメーター

*pScheduler*<br/>
この実行リソースを削除する要求を行っているスケジューラへのインターフェイス。

### <a name="remarks"></a>Remarks

このメソッドを使用して、スタンドアロンの実行リソースと Resource Manager への仮想プロセッサ ルートに関連付けられている実行リソースを返します。

メソッドのいずれかから受信した場合、これは、スタンドアロンの実行リソース[ischedulerproxy::subscribecurrentthread](ischedulerproxy-structure.md#subscribecurrentthread)または[ischedulerproxy::requestinitialvirtualprocessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)を呼び出すと、メソッド`Remove`にリソースが作成されたスレッドのサブスクリプションが終了を表します。 スケジューラのプロキシをシャット ダウンする前にスレッドのすべてのサブスクリプションを終了する必要があり、呼び出す必要がある`Remove`サブスクリプションを作成したスレッドから。

仮想プロセッサ ルート、すぎる、によって返される Resource Manager への呼び出し、`Remove`メソッド、ため、インターフェイス`IVirtualProcessorRoot`継承、`IExecutionResource`インターフェイス。 仮想プロセッサ ルートをへの呼び出しに応答で返す必要があります、 [ischeduler::removevirtualprocessors](ischeduler-structure.md#removevirtualprocessors)メソッド、またはをオーバーサブスク ライブの仮想プロセッサ ルートから取得したが完了したら、 [Ischedulerproxy::createoversubscriber](ischedulerproxy-structure.md#createoversubscriber)メソッド。 仮想プロセッサ ルートでは、制限がないスレッドを呼び出すことができます、`Remove`メソッド。

`invalid_argument` 場合にスローされるパラメーター`pScheduler`に設定されている`NULL`します。

`invalid_operation` 場合にスローされるパラメーター`pScheduler`は、現在のスレッドがスレッドのサブスクリプションを作成したスレッドと異なる場合、または、スタンドアロンの実行リソースでは、この実行リソースが作成されたこと、スケジューラから異なる。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)
