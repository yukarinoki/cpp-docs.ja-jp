---
title: ISchedulerProxy 構造体
ms.date: 11/04/2016
f1_keywords:
- ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::BindContext
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::CreateOversubscriber
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::RequestInitialVirtualProcessors
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::Shutdown
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::SubscribeCurrentThread
- CONCRTRM/concurrency::ISchedulerProxy::ISchedulerProxy::UnbindContext
helpviewer_keywords:
- ISchedulerProxy structure
ms.assetid: af416973-7a1c-4c30-aa3b-4161c2aaea54
ms.openlocfilehash: f4a9e79c2da56406610ad6da08fb438e2f92923d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368154"
---
# <a name="ischedulerproxy-structure"></a>ISchedulerProxy 構造体

スケジューラは、このインターフェイスを使用してコンカレンシー ランタイムのリソース マネージャーと通信して、リソース割り当てをネゴシエートします。

## <a name="syntax"></a>構文

```cpp
struct ISchedulerProxy;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[を指定します。](#bindcontext)|実行コンテキストがスレッド プロキシに関連付けられていない場合は、そのコンテキストをスレッド プロキシに関連付けます。|
|[Iスケジューラプロキシ::オーバーサブスクライバーの作成](#createoversubscriber)|既存の実行リソースに関連付けられたハードウェア スレッドに、新しい仮想プロセッサ ルートを作成します。|
|[I スケジューラプロキシ::要求初期仮想プロセッサ](#requestinitialvirtualprocessors)|仮想プロセッサ ルートの初期割り当てを要求します。 すべての仮想プロセッサ ルートは、スケジューラの作業を実行できる 1 つのスレッドを実行する機能を表します。|
|[I スケジューラプロキシ::シャットダウン](#shutdown)|スケジューラがシャットダウン中であることをリソース マネージャーに通知します。 これにより、リソース マネージャーは直ちにスケジューラに付与されているすべてのリソースを再利用します。|
|[をサブスクライブします。](#subscribecurrentthread)|現在のスレッドをリソース マネージャーに登録し、このスケジューラに関連付けます。|
|[を使用します。](#unbindcontext)|パラメーターで指定された実行コンテキストからスレッド プロキシの`pContext`関連付けを解除し、スレッド プロキシ ファクトリの空きプールに返します。 このメソッドは[、ISchedulerProxy::BindContext](#bindcontext)メソッドを介してバインドされ、IThreadProxy::SwitchTo メソッド呼び出し`pContext`のパラメーターとして[IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto)まだ開始されていない実行コンテキストでのみ呼び出されます。|

## <a name="remarks"></a>解説

リソース マネージャーは`ISchedulerProxy`[、IResourceManager::RegisterScheduler](iresourcemanager-structure.md#registerscheduler)メソッドを使用して登録するすべてのスケジューラにインターフェイスを渡します。

## <a name="inheritance-hierarchy"></a>継承階層

`ISchedulerProxy`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="ischedulerproxybindcontext-method"></a><a name="bindcontext"></a>メソッドをバインドします。

実行コンテキストがスレッド プロキシに関連付けられていない場合は、そのコンテキストをスレッド プロキシに関連付けます。

```cpp
virtual void BindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
スレッド プロキシに関連付ける実行コンテキストへのインターフェイス。

### <a name="remarks"></a>解説

通常[、IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto)メソッドは、スレッド プロキシをオンデマンドで実行コンテキストにバインドします。 ただし、メソッドが既にバインドされているコンテキストに切り替わるように、事前にコンテキストを`SwitchTo`バインドする必要がある状況があります。 これは、メモリを割り当てるメソッドを呼び出すことができないため、UMS スケジューリング コンテキストでの場合であり、スレッド プロキシ のバインドは、スレッド プロキシ ファクトリの空きプールでスレッド プロキシをすぐに利用できない場合、メモリ割り当てを伴う可能性があります。

`invalid_argument`パラメータに値`NULL`が指定`pContext`されている場合にスローされます。

## <a name="ischedulerproxycreateoversubscriber-method"></a><a name="createoversubscriber"></a>Iスケジューラプロキシ::Createオーバーサブスクライバメソッド

既存の実行リソースに関連付けられたハードウェア スレッドに、新しい仮想プロセッサ ルートを作成します。

```cpp
virtual IVirtualProcessorRoot* CreateOversubscriber(_Inout_ IExecutionResource* pExecutionResource) = 0;
```

### <a name="parameters"></a>パラメーター

*を使用します。*<br/>
オーバー`IExecutionResource`サブスクライブするハードウェア スレッドを表すインターフェイス。

### <a name="return-value"></a>戻り値

`IVirtualProcessorRoot` インターフェイスです。

### <a name="remarks"></a>解説

スケジューラが特定のハードウェア スレッドを限られた時間にわたってオーバーサブスクライブする場合は、このメソッドを使用します。 仮想プロセッサ ルートを使用したら、インターフェイスの[Remove](iexecutionresource-structure.md#remove)メソッドを呼び出して、リソース マネージャーに返`IVirtualProcessorRoot`す必要があります。

インターフェイスは`IExecutionResource`インターフェイスから継承するため、既存の仮想プロセッサ ルート`IVirtualProcessorRoot`をオーバーサブスクライブすることもできます。

## <a name="ischedulerproxyrequestinitialvirtualprocessors-method"></a><a name="requestinitialvirtualprocessors"></a>メソッドを呼び出します。

仮想プロセッサ ルートの初期割り当てを要求します。 すべての仮想プロセッサ ルートは、スケジューラの作業を実行できる 1 つのスレッドを実行する機能を表します。

```cpp
virtual IExecutionResource* RequestInitialVirtualProcessors(bool doSubscribeCurrentThread) = 0;
```

### <a name="parameters"></a>パラメーター

*現在のスレッドをサブスクライブします。*<br/>
リソース割り当て時に現在のスレッドをサブスクライブし、そのアカウントを作成するかどうか。

### <a name="return-value"></a>戻り値

パラメーター`IExecutionResource``doSubscribeCurrentThread`の値が**true**の場合、現在のスレッドのインターフェイス。 値が**false**の場合、メソッドは NULL を返します。

### <a name="remarks"></a>解説

スケジューラは、作業を実行する前に、このメソッドを使用してリソース マネージャーに仮想プロセッサ ルートを要求する必要があります。 リソース マネージャーは[、IScheduler::GetPolicy](ischeduler-structure.md#getpolicy)を`MinConcurrency``MaxConcurrency`使用してスケジューラのポリシーにアクセスし、ポリシー キーの値`TargetOversubscriptionFactor`を使用して、最初にスケジューラに割り当てるハードウェア スレッドの数と、各ハードウェア スレッドに対して作成する仮想プロセッサ ルートの数を決定します。 スケジューラ ポリシーを使用してスケジューラの初期割り当てを決定する方法の詳細については、「 [PolicyElementKey](concurrency-namespace-enums.md)」を参照してください。

リソース マネージャーは、仮想プロセッサ ルートの一覧を持つメソッド[IScheduler::AddVirtualProcessors を](ischeduler-structure.md#addvirtualprocessors)呼び出すことによって、スケジューラにリソースを付与します。 このメソッドは、このメソッドが戻る前にスケジューラへのコールバックとして呼び出されます。

スケジューラがパラメーター`doSubscribeCurrentThread`を**true**に設定して現在のスレッドのサブスクリプションを要求した場合、`IExecutionResource`メソッドはインターフェイスを返します。 サブスクリプションは、後で[IExecutionResource::Remove](iexecutionresource-structure.md#remove)メソッドを使用して終了する必要があります。

選択されているハードウェア スレッドを決定する場合、Resource Manager はプロセッサ ノードのアフィニティの最適化を試みます。 現在のスレッドに対してサブスクリプションが要求された場合、現在のスレッドがこのスケジューラに割り当てられた作業に参加しようとしていることを示します。 このような場合、割り当てられた仮想プロセッサ のルートは、現在のスレッドが実行されているプロセッサ ノード上に配置されます (可能な場合)。

スレッドをサブスクライブすると、基になるハードウェア スレッドのサブスクリプション レベルが 1 つ増えます。 サブスクリプションが終了すると、サブスクリプション レベルが 1 つ減ります。 サブスクリプション レベルの詳細については[、「IExecution リソース::現在のサブスクリプションレベル](iexecutionresource-structure.md#currentsubscriptionlevel)」を参照してください。

## <a name="ischedulerproxyshutdown-method"></a><a name="shutdown"></a>Iスケジューラプロキシ::シャットダウンメソッド

スケジューラがシャットダウン中であることをリソース マネージャーに通知します。 これにより、リソース マネージャーは直ちにスケジューラに付与されているすべてのリソースを再利用します。

```cpp
virtual void Shutdown() = 0;
```

### <a name="remarks"></a>解説

メソッド`IExecutionContext``ISchedulerProxy::RequestInitialVirtualProcessors`を使用して外部スレッドをサブスクライブした結果としてスケジューラが受信したすべてのインターフェイス、または`ISchedulerProxy::SubscribeCurrentThread`スケジューラがシャットダウンする前に、`IExecutionResource::Remove`リソース マネージャーに返す必要があります。

スケジューラに非アクティブ化された仮想プロセッサ ルートがある場合は[、IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate)を使用してそれらをアクティブにし、実行しているスレッド プロキシが`Dispatch`、スケジューラ プロキシで呼び出す`Shutdown`前にディスパッチしている実行コンテキストのメソッドを残しておく必要があります。

すべての仮想プロセッサ ルートはシャットダウン時にリソース マネージャーに返されるため、スケジューラは、リソース マネージャーが`Remove`メソッドの呼び出しを介して与えられた仮想プロセッサ ルートをすべて個別に返す必要はありません。

## <a name="ischedulerproxysubscribecurrentthread-method"></a><a name="subscribecurrentthread"></a>メソッドをサブスクライブします。

現在のスレッドをリソース マネージャーに登録し、このスケジューラに関連付けます。

```cpp
virtual IExecutionResource* SubscribeCurrentThread() = 0;
```

### <a name="return-value"></a>戻り値

ランタイム`IExecutionResource`の現在のスレッドを表すインターフェイス。

### <a name="remarks"></a>解説

スケジューラやその他のスケジューラにリソースを割り当てながら、リソース マネージャーが現在のスレッドを考慮する場合は、このメソッドを使用します。 スケジューラがリソース マネージャーから受け取る仮想プロセッサ ルートと共に、スレッドがスケジューラにキューに入っている作業に参加する予定がある場合に特に便利です。 リソース マネージャは、情報を使用して、システム上のハードウェア スレッドの不必要なオーバーサブスクリプションを防ぎます。

このメソッドを使用して受信した実行リソースは[、IExecutionResource::Remove](iexecutionresource-structure.md#remove)メソッドを使用してリソース マネージャーに返される必要があります。 メソッドを呼び出`Remove`すスレッドは、以前に`SubscribeCurrentThread`メソッドを呼び出したスレッドと同じスレッドである必要があります。

スレッドをサブスクライブすると、基になるハードウェア スレッドのサブスクリプション レベルが 1 つ増えます。 サブスクリプションが終了すると、サブスクリプション レベルが 1 つ減ります。 サブスクリプション レベルの詳細については[、「IExecution リソース::現在のサブスクリプションレベル](iexecutionresource-structure.md#currentsubscriptionlevel)」を参照してください。

## <a name="ischedulerproxyunbindcontext-method"></a><a name="unbindcontext"></a>メソッドをバインドします。

パラメーターで指定された実行コンテキストからスレッド プロキシの`pContext`関連付けを解除し、スレッド プロキシ ファクトリの空きプールに返します。 このメソッドは[、ISchedulerProxy::BindContext](#bindcontext)メソッドを介してバインドされ、IThreadProxy::SwitchTo メソッド呼び出し`pContext`のパラメーターとして[IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto)まだ開始されていない実行コンテキストでのみ呼び出されます。

```cpp
virtual void UnbindContext(_Inout_ IExecutionContext* pContext) = 0;
```

### <a name="parameters"></a>パラメーター

*pContext*<br/>
スレッド プロキシとの関連付けを解除する実行コンテキスト。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[IScheduler 構造体](ischeduler-structure.md)<br/>
[IThreadProxy 構造体](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager 構造体](iresourcemanager-structure.md)
