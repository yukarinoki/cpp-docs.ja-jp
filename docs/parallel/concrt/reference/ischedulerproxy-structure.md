---
title: ISchedulerProxy 構造体 |Microsoft Docs
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
ms.openlocfilehash: 72fa49d763159385607330231994d15952f0c771
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163141"
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
|[ISchedulerProxy::BindContext](#bindcontext)|いずれかで関連付けられていない場合は、スレッド プロキシを使用して、実行コンテキストを関連付けます。|
|[ISchedulerProxy::CreateOversubscriber](#createoversubscriber)|既存の実行リソースに関連付けられたハードウェア スレッドで新しい仮想プロセッサ ルートを作成します。|
|[ISchedulerProxy::RequestInitialVirtualProcessors](#requestinitialvirtualprocessors)|仮想プロセッサ ルートの最初の割り当てを要求します。 すべての仮想プロセッサ ルートでは、スケジューラの作業を実行できる 1 つのスレッドを実行する機能を表します。|
|[ISchedulerProxy::Shutdown](#shutdown)|スケジューラがシャット ダウンしてリソース マネージャーに通知します。 これをすぐに、スケジューラに付与されたすべてのリソースを解放する Resource Manager になります。|
|[ISchedulerProxy::SubscribeCurrentThread](#subscribecurrentthread)|このスケジューラに関連付けられた、Resource Manager で、現在のスレッドを登録します。|
|[ISchedulerProxy::UnbindContext](#unbindcontext)|指定された実行コンテキストからスレッド プロキシの関連付けを解除、`pContext`パラメーターと、スレッド プロキシ ファクトリの空きプールに返します。 このメソッドを使用してバインドされた実行コンテキストにのみ呼び出すことがあります、 [ischedulerproxy::bindcontext](#bindcontext)メソッド中でまだ開始されていないと、`pContext`のパラメーター、 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)メソッドの呼び出し。|

## <a name="remarks"></a>Remarks

リソース マネージャーに渡して、`ISchedulerProxy`インターフェイスを使用して登録するすべてのスケジューラを[iresourcemanager::registerscheduler](iresourcemanager-structure.md#registerscheduler)メソッド。

## <a name="inheritance-hierarchy"></a>継承階層

`ISchedulerProxy`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="bindcontext"></a>  Ischedulerproxy::bindcontext メソッド

いずれかで関連付けられていない場合は、スレッド プロキシを使用して、実行コンテキストを関連付けます。

```
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
関連付けるスレッド プロキシを使用した実行コンテキストへのインターフェイス。

### <a name="remarks"></a>Remarks

通常、 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)メソッドでは、スレッド プロキシは要求時に実行コンテキストにバインドします。 ある、ただし、いることを確認するには、事前にコンテキストをバインドする必要がある場合、`SwitchTo`メソッドが既にバインドされているコンテキストに切り替えます。 これはスケジュール コンテキスト、メモリの割り当てメソッドを呼び出すことはできません UMS のケースであり、スレッド プロキシを工場出荷時の空きプールのスレッド プロキシがすぐに使用できない場合に、メモリの割り当て、スレッド プロキシをバインドする必要があります。

`invalid_argument` 場合にスローされるパラメーター `pContext` 、値を持つ`NULL`します。

##  <a name="createoversubscriber"></a>  Ischedulerproxy::createoversubscriber メソッド

既存の実行リソースに関連付けられたハードウェア スレッドで新しい仮想プロセッサ ルートを作成します。

```
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>パラメーター

*pExecutionResource*<br/>
`IExecutionResource`オーバーサブスク ライブするハードウェア スレッドを表すインターフェイスです。

### <a name="return-value"></a>戻り値

`IVirtualProcessorRoot` インターフェイス。

### <a name="remarks"></a>Remarks

スケジューラが一定時間の特定のハードウェア スレッドをオーバーサブスク ライブするときに、このメソッドを使用します。 完了すると、仮想プロセッサ ルートとする必要があります値を返す、resource manager を呼び出すことによって、[削除](iexecutionresource-structure.md#remove)メソッドを`IVirtualProcessorRoot`インターフェイス。

でもオーバーサブスク ライブできます既存の仮想プロセッサ ルートのため、`IVirtualProcessorRoot`インターフェイスから継承、`IExecutionResource`インターフェイス。

##  <a name="requestinitialvirtualprocessors"></a>  Ischedulerproxy::requestinitialvirtualprocessors メソッド

仮想プロセッサ ルートの最初の割り当てを要求します。 すべての仮想プロセッサ ルートでは、スケジューラの作業を実行できる 1 つのスレッドを実行する機能を表します。

```
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>パラメーター

*doSubscribeCurrentThread*<br/>
現在のスレッドを購読し、リソースの割り当て中に考慮するかどうか。

### <a name="return-value"></a>戻り値

`IExecutionResource`インターフェイスの現在のスレッドの場合、パラメーター `doSubscribeCurrentThread` 、値を持つ**true**します。 値が場合**false**NULL が返されます。

### <a name="remarks"></a>Remarks

スケジューラは作業を実行する前に、Resource Manager からの仮想プロセッサ ルートを要求するのにこのメソッドを使用してください。 Resource Manager は、スケジューラのポリシーへのアクセスを使用して[ischeduler::getpolicy](ischeduler-structure.md#getpolicy)ポリシー キーの値を使用して`MinConcurrency`、`MaxConcurrency`と`TargetOversubscriptionFactor`に割り当てるハードウェア スレッドの数を決定する、スケジューラ最初に、すべてのハードウェア スレッドを作成する方法の多くの仮想プロセッサ ルート。 スケジューラの初期の割り当てを判断するスケジューラ ポリシーを使用する方法の詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)します。

Resource Manager は、メソッドを呼び出して、スケジューラにリソースを付与[ischeduler::addvirtualprocessors](ischeduler-structure.md#addvirtualprocessors)仮想プロセッサ ルートの一覧。 メソッドには、このメソッドが戻る前に、スケジューラにコールバックとして呼び出さします。

スケジューラがパラメーターを設定して、現在のスレッドのサブスクリプションを要求するかどうか`doSubscribeCurrentThread`に**true**、メソッドを返します、`IExecutionResource`インターフェイス。 使用して、後で、サブスクリプションを終了する必要があります、 [iexecutionresource::remove](iexecutionresource-structure.md#remove)メソッド。

ハードウェア スレッドが選択されているかを決定するときに、リソース マネージャーはプロセッサ ノード アフィニティを最適化しようとします。 現在のスレッドのサブスクリプションが要求された場合は、現在のスレッドがこのスケジューラに割り当てられている作業に参加することを示しています。 このような場合は、割り当てられた仮想プロセッサ ルートは、現在のスレッドが可能であれば、実行するプロセッサのノードにあります。

スレッドのサブスクライブは、基になるハードウェア スレッドのサブスクリプション レベルを 1 つずつ増加します。 サブスクリプションが終了したときにいずれかによって、サブスクリプション レベルが減少します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。

##  <a name="shutdown"></a>  Ischedulerproxy::shutdown メソッド

スケジューラがシャット ダウンしてリソース マネージャーに通知します。 これをすぐに、スケジューラに付与されたすべてのリソースを解放する Resource Manager になります。

```
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>Remarks

すべて`IExecutionContext`インターフェイスのメソッドを使用して外部のスレッドの購読の結果として受信したスケジューラ`ISchedulerProxy::RequestInitialVirtualProcessors`または`ISchedulerProxy::SubscribeCurrentThread`Resource Manager に返す必要があるを使用して`IExecutionResource::Remove`スケジューラでは、自身をシャット ダウンする前にします。

非アクティブ化されたいずれかの仮想プロセッサ ルート、スケジューラがある場合は、それらをアクティブ化する必要がありますを使用して[ivirtualprocessorroot::activate](ivirtualprocessorroot-structure.md#activate)のままにして実行するスレッド プロキシがあると、`Dispatch`メソッドの実行呼び出す前に、ディスパッチはコンテキスト`Shutdown`スケジューラ プロキシ。

スケジューラを個別に返すすべての仮想プロセッサ ルートへの呼び出しによって付与 Resource Manager の必要はありません、`Remove`メソッドすべての仮想プロセッサ ルートはシャット ダウン時に Resource Manager に返されるためです。

##  <a name="subscribecurrentthread"></a>  Ischedulerproxy::subscribecurrentthread メソッド

このスケジューラに関連付けられた、Resource Manager で、現在のスレッドを登録します。

```
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>戻り値

`IExecutionResource`ランタイムでは、現在のスレッドを表すインターフェイスします。

### <a name="remarks"></a>Remarks

リソース マネージャーは、スケジューラ、およびその他のスケジューラにリソースを割り当てているときに、現在のスレッドに対応する場合は、このメソッドを使用します。 作業に参加するスレッドのプランは、スケジューラは、Resource Manager からの受信仮想プロセッサ ルートと、スケジューラ キューに置かれたときに特に便利です。 Resource Manager では、システム上のハードウェア スレッドの不要なオーバー サブスクリプションを防ぐために情報を使用します。

このメソッドを使用して受信した実行リソースは Resource Manager へ返す必要があるを使用して、 [iexecutionresource::remove](iexecutionresource-structure.md#remove)メソッド。 呼び出すスレッド、`Remove`メソッドは以前に呼び出されている同じスレッドである必要があります、`SubscribeCurrentThread`メソッド。

スレッドのサブスクライブは、基になるハードウェア スレッドのサブスクリプション レベルを 1 つずつ増加します。 サブスクリプションが終了したときにいずれかによって、サブスクリプション レベルが減少します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。

##  <a name="unbindcontext"></a>  Ischedulerproxy::unbindcontext メソッド

指定された実行コンテキストからスレッド プロキシの関連付けを解除、`pContext`パラメーターと、スレッド プロキシ ファクトリの空きプールに返します。 このメソッドを使用してバインドされた実行コンテキストにのみ呼び出すことがあります、 [ischedulerproxy::bindcontext](#bindcontext)メソッド中でまだ開始されていないと、`pContext`のパラメーター、 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)メソッドの呼び出し。

```
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
そのスレッド プロキシから関連付けを解除する実行コンテキスト。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)<br/>
[IThreadProxy 構造体](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager 構造体](iresourcemanager-structure.md)
