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
ms.openlocfilehash: 4305948aa4e5da36023c1d4fe8b0b84aa4d59e23
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377310"
---
# <a name="iexecutionresource-structure"></a>IExecutionResource 構造体

ハードウェア スレッドの抽象化です。

## <a name="syntax"></a>構文

```cpp
struct IExecutionResource;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[リソース::現在のサブスクリプションレベル](#currentsubscriptionlevel)|この実行リソースが表す、基になるハードウェア スレッドに現在関連付けられているアクティブな仮想プロセッサ ルートとサブスクライブされた外部スレッドの数を返します。|
|[を指定します。](#getexecutionresourceid)|この実行リソースが表すハードウェア スレッドの一意の識別子を返します。|
|[をリソースに取り込みます。](#getnodeid)|この実行リソースが属するプロセッサ ノードの一意の識別子を返します。|
|[I実行リソース::削除](#remove)|この実行リソースをリソース マネージャーに返します。|

## <a name="remarks"></a>解説

実行リソースは、スタンドアロンであるか、仮想プロセッサ ルートに関連付けることができます。 スタンドアロン実行リソースは、アプリケーションのスレッドがスレッド サブスクリプションを作成するときに作成されます。 メソッド[ISchedulerProxy::サブスクライブスレッド](ischedulerproxy-structure.md#subscribecurrentthread)と[I スケジューラプロキシ::要求初期仮想プロセッサは](ischedulerproxy-structure.md#requestinitialvirtualprocessors)スレッド サブスクリプションを作成し`IExecutionResource`、サブスクリプションを表すインターフェイスを返します。 スレッド サブスクリプションの作成は、特定のスレッドがスケジューラにキューに入っている作業に参加することをリソース マネージャーに通知する方法です。 リソース マネージャは、この情報を使用して、可能な限りハードウェア スレッドをオーバーサブスクライブしないようにします。

## <a name="inheritance-hierarchy"></a>継承階層

`IExecutionResource`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="iexecutionresourcecurrentsubscriptionlevel-method"></a><a name="currentsubscriptionlevel"></a>メソッドを使用します。

この実行リソースが表す、基になるハードウェア スレッドに現在関連付けられているアクティブな仮想プロセッサ ルートとサブスクライブされた外部スレッドの数を返します。

```cpp
virtual unsigned int CurrentSubscriptionLevel() const = 0;
```

### <a name="return-value"></a>戻り値

現在のサブスクリプション レベル。

### <a name="remarks"></a>解説

サブスクリプション レベルは、実行中のスレッドの数をハードウェア スレッドに関連付ける数を示します。 これには、リソース マネージャーがサブスクライブされたスレッドの形式で認識しているスレッドと、スレッド プロキシをアクティブに実行している仮想プロセッサ ルートのみが含まれます。

メソッドを呼び出す[ISchedulerProxy::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread)、またはパラメーター`doSubscribeCurrentThread`が**true に**設定されたメソッド[ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)を呼び出すと、ハードウェア スレッドのサブスクリプション レベルが 1 ずつ増加します。 また、サブスクリプションを`IExecutionResource`表すインターフェイスも返します。 [IExecutionResource::Remove](#remove)への対応する呼び出しは、ハードウェア スレッドのサブスクリプション レベルを 1 つ減分します。

メソッドを使用して仮想プロセッサ ルートをアクティブ化する動作[IVirtualProcessorRoot::Activate](ivirtualprocessorroot-structure.md#activate)は、ハードウェア スレッドのサブスクリプション レベルを 1 ずつインクリメントします。 アクティブ化された仮想[プロセッサ :D ルート](ivirtualprocessorroot-structure.md#deactivate)で呼び出されたときに、サブスクリプション レベルを 1 つずつ[削除](#remove)するメソッド 。

リソース マネージャーは、スケジューラ間でリソースを移動するタイミングを決定する方法の 1 つとして、サブスクリプション レベル情報を使用します。

## <a name="iexecutionresourcegetexecutionresourceid-method"></a><a name="getexecutionresourceid"></a>メソッドを実行します。

この実行リソースが表すハードウェア スレッドの一意の識別子を返します。

```cpp
virtual unsigned int GetExecutionResourceId() const = 0;
```

### <a name="return-value"></a>戻り値

この実行リソースの基になるハードウェア スレッドの一意の識別子。

### <a name="remarks"></a>解説

各ハードウェア スレッドには、同時実行ランタイムによって一意の識別子が割り当てられます。 複数の実行リソースが関連付けられているハードウェア スレッドの場合、すべての実行リソース識別子が同じになります。

## <a name="iexecutionresourcegetnodeid-method"></a><a name="getnodeid"></a>メソッドを取得します。

この実行リソースが属するプロセッサ ノードの一意の識別子を返します。

```cpp
virtual unsigned int GetNodeId() const = 0;
```

### <a name="return-value"></a>戻り値

プロセッサ ノードの一意の識別子。

### <a name="remarks"></a>解説

同時実行ランタイムは、プロセッサ ノードのグループでシステム上のハードウェア スレッドを表します。 ノードは通常、システムのハードウェア トポロジから派生します。 たとえば、特定のソケットまたは特定の NUMA ノード上のすべてのプロセッサが同じプロセッサ ノードに属している場合があります。 リソース マネージャは、システム上のプロセッサ ノードの合計数`0`を`nodeCount`表す、 `nodeCount - 1`( を含む ) で始まるこれらのノードに一意の識別子を割り当てます。

ノードの数は、関数[から](concurrency-namespace-functions.md)取得できます。

## <a name="iexecutionresourceremove-method"></a><a name="remove"></a>メソッドの削除

この実行リソースをリソース マネージャーに返します。

```cpp
virtual void Remove(_Inout_ IScheduler* pScheduler) = 0;
```

### <a name="parameters"></a>パラメーター

*スケジューラー*<br/>
この実行リソースを削除する要求を行うスケジューラへのインターフェイス。

### <a name="remarks"></a>解説

このメソッドは、スタンドアロンの実行リソースと、仮想プロセッサ ルートに関連付けられた実行リソースをリソース マネージャに返すために使います。

これがメソッド[ISchedulerProxy:::SubscribeCurrentThread](ischedulerproxy-structure.md#subscribecurrentthread)または[ISchedulerProxy::RequestInitialVirtualProcessors](ischedulerproxy-structure.md#requestinitialvirtualprocessors)のいずれかから受け取ったスタンドアロンの実行リソースである場合`Remove`、メソッドを呼び出すと、リソースが表すために作成されたスレッド サブスクリプションが終了します。 スケジューラ プロキシをシャットダウンする前にすべてのスレッド サブスクリプションを終了する必要があり、サブスクリプションを`Remove`作成したスレッドから呼び出す必要があります。

仮想プロセッサ ルートも、インターフェイス`Remove``IVirtualProcessorRoot`がインターフェイスから継承するため、メソッドを呼び出すことによってリソース マネージャーに`IExecutionResource`返すことができます。 [IScheduler::RemoveVirtualProcessors](ischeduler-structure.md#removevirtualprocessors)メソッドの呼び出しに応答して仮想プロセッサ ルートを返すか[、ISchedulerProxy::CreateOver サブスクライバ](ischedulerproxy-structure.md#createoversubscriber)メソッドから取得したオーバーサブスクライブされた仮想プロセッサ ルートで完了した場合に、仮想プロセッサ ルートを返す必要があります。 仮想プロセッサ ルートの場合、`Remove`メソッドを呼び出すことができるスレッドに制限はありません。

`invalid_argument`パラメータ`pScheduler`が`NULL`に設定されている場合にスローされます。

`invalid_operation`この実行リソース`pScheduler`が作成されたスケジューラとパラメーターが異なる場合、またはスタンドアロンの実行リソースを使用して現在のスレッドがスレッド サブスクリプションを作成したスレッドと異なる場合はスローされます。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)
