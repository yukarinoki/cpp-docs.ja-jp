---
description: '詳細については、次を参照してください: IScheduler 構造体'
title: IScheduler 構造体
ms.date: 11/04/2016
f1_keywords:
- IScheduler
- CONCRTRM/concurrency::IScheduler
- CONCRTRM/concurrency::IScheduler::IScheduler::AddVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::GetId
- CONCRTRM/concurrency::IScheduler::IScheduler::GetPolicy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyBusy
- CONCRTRM/concurrency::IScheduler::IScheduler::NotifyResourcesExternallyIdle
- CONCRTRM/concurrency::IScheduler::IScheduler::RemoveVirtualProcessors
- CONCRTRM/concurrency::IScheduler::IScheduler::Statistics
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
ms.openlocfilehash: 3a99ea5041c9d1146bb2247c1dcac54ff2fb7cf1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334468"
---
# <a name="ischeduler-structure"></a>IScheduler 構造体

作業スケジューラの抽象化のインターフェイスです。 コンカレンシー ランタイムのリソース マネージャーは、このインターフェイスを使用して作業スケジューラと通信します。

## <a name="syntax"></a>構文

```cpp
struct IScheduler;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IScheduler:: AddVirtualProcessors](#addvirtualprocessors)|スケジューラに、使用するための一連の仮想プロセッサルートを提供します。 各 `IVirtualProcessorRoot` インターフェイスは、スケジューラに代わって処理を実行できる1つのスレッドを実行する権限を表します。|
|[IScheduler:: GetId](#getid)|スケジューラの一意の識別子を返します。|
|[IScheduler:: GetPolicy](#getpolicy)|スケジューラのポリシーのコピーを返します。 Scheduler ポリシーの詳細については、「スケジューラ [ポリシー](schedulerpolicy-class.md)」を参照してください。|
|[IScheduler:: NotifyResourcesExternallyBusy](#notifyresourcesexternallybusy)|このスケジューラに、配列内の仮想プロセッサルートのセットによって表されるハードウェアスレッド `ppVirtualProcessorRoots` が、現在、他のスケジューラによって使用されていることを通知します。|
|[IScheduler:: NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|このスケジューラに、配列内の仮想プロセッサルートのセットによって表されるハードウェアスレッド `ppVirtualProcessorRoots` が、他のスケジューラによって使用されていないことを通知します。|
|[IScheduler:: RemoveVirtualProcessors](#removevirtualprocessors)|以前にこのスケジューラに割り当てられた仮想プロセッサルートの削除を開始します。|
|[IScheduler:: Statistics](#statistics)|タスクの到着と完了率に関する情報を提供し、スケジューラのキューの長さを変更します。|

## <a name="remarks"></a>解説

リソースマネージャーと通信するカスタムスケジューラを実装する場合は、インターフェイスの実装を提供する必要があり `IScheduler` ます。 このインターフェイスは、スケジューラとリソースマネージャーの間の通信の双方向チャネルの1つの端です。 もう一方の端は、 `IResourceManager` `ISchedulerProxy` リソースマネージャーによって実装されるインターフェイスとインターフェイスによって表されます。

## <a name="inheritance-hierarchy"></a>継承階層

`IScheduler`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm. h

**名前空間:** concurrency

## <a name="ischeduleraddvirtualprocessors-method"></a><a name="addvirtualprocessors"></a> IScheduler:: AddVirtualProcessors メソッド

スケジューラに、使用するための一連の仮想プロセッサルートを提供します。 各 `IVirtualProcessorRoot` インターフェイスは、スケジューラに代わって処理を実行できる1つのスレッドを実行する権限を表します。

```cpp
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*ppVirtualProcessorRoots*<br/>
`IVirtualProcessorRoot`スケジューラに追加されている仮想プロセッサルートを表すインターフェイスの配列。

*count*<br/>
`IVirtualProcessorRoot`配列内のインターフェイスの数。

### <a name="remarks"></a>解説

リソースマネージャーは、メソッドを呼び出して、 `AddVirtualProcessor` 最初の仮想プロセッサルートのセットをスケジューラに付与します。 また、スケジューラ間でリソースをバランスするときに、メソッドを呼び出して、仮想プロセッサルートをスケジューラに追加することもできます。

## <a name="ischedulergetid-method"></a><a name="getid"></a> IScheduler:: GetId メソッド

スケジューラの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

一意の整数識別子。

### <a name="remarks"></a>解説

インターフェイスを実装するオブジェクトの一意の識別子を取得するには、 [GetSchedulerId](concurrency-namespace-functions.md) 関数を使用する必要があり `IScheduler` ます。その前に、リソースマネージャーによって提供されるメソッドのパラメーターとしてインターフェイスを使用します。 関数が呼び出されたときに、同じ識別子を返すことが想定されてい `GetId` ます。

別のソースから取得した識別子は、未定義の動作を引き起こす可能性があります。

## <a name="ischedulergetpolicy-method"></a><a name="getpolicy"></a> IScheduler:: GetPolicy メソッド

スケジューラのポリシーのコピーを返します。 Scheduler ポリシーの詳細については、「スケジューラ [ポリシー](schedulerpolicy-class.md)」を参照してください。

```cpp
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>戻り値

スケジューラのポリシーのコピー。

## <a name="ischedulernotifyresourcesexternallybusy-method"></a><a name="notifyresourcesexternallybusy"></a> IScheduler:: NotifyResourcesExternallyBusy メソッド

このスケジューラに、配列内の仮想プロセッサルートのセットによって表されるハードウェアスレッド `ppVirtualProcessorRoots` が、現在、他のスケジューラによって使用されていることを通知します。

```cpp
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*ppVirtualProcessorRoots*<br/>
`IVirtualProcessorRoot`他のスケジューラがビジー状態になったハードウェアスレッドに関連付けられたインターフェイスの配列。

*count*<br/>
`IVirtualProcessorRoot`配列内のインターフェイスの数。

### <a name="remarks"></a>解説

特定のハードウェアスレッドを同時に複数のスケジューラに割り当てることができます。 その理由の1つは、リソースを共有せずに、すべてのスケジューラの最小同時実行数を満たすために、システム上に十分なハードウェアスレッドがないことです。 もう1つの可能性として、所有しているスケジューラが非アクティブ化されているハードウェアスレッド上のすべての仮想プロセッサルートから、リソースが一時的に他のスケジューラに割り当てられていない可能性もあります。

ハードウェアスレッドのサブスクリプションレベルは、そのハードウェアスレッドに関連付けられている、サブスクライブしているスレッドとアクティブ化された仮想プロセッサのルートの数によって示されます。 特定のスケジューラの観点から見ると、ハードウェアスレッドの外部サブスクリプションレベルは、他のスケジューラが貢献するサブスクリプションの部分です。 リソースが外部でビジー状態であることを示す通知は、ハードウェアスレッドの外部サブスクリプションレベルがゼロから正の区域に移動したときにスケジューラに送信されます。

このメソッドによる通知は、ポリシーキーの値がポリシーキーの値と同じポリシーを持つスケジューラにのみ送信され `MinConcurrency` `MaxConcurrency` ます。 Scheduler ポリシーの詳細については、「スケジューラ [ポリシー](schedulerpolicy-class.md)」を参照してください。

通知を受け取るスケジューラは、作成時に初期通知のセットを取得し、それが割り当てられたリソースが外部でビジー状態かアイドル状態かを通知します。

## <a name="ischedulernotifyresourcesexternallyidle-method"></a><a name="notifyresourcesexternallyidle"></a> IScheduler:: NotifyResourcesExternallyIdle メソッド

このスケジューラに、配列内の仮想プロセッサルートのセットによって表されるハードウェアスレッド `ppVirtualProcessorRoots` が、他のスケジューラによって使用されていないことを通知します。

```cpp
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*ppVirtualProcessorRoots*<br/>
`IVirtualProcessorRoot`他のスケジューラがアイドル状態になったハードウェアスレッドに関連付けられたインターフェイスの配列。

*count*<br/>
`IVirtualProcessorRoot`配列内のインターフェイスの数。

### <a name="remarks"></a>解説

特定のハードウェアスレッドを同時に複数のスケジューラに割り当てることができます。 その理由の1つは、リソースを共有せずに、すべてのスケジューラの最小同時実行数を満たすために、システム上に十分なハードウェアスレッドがないことです。 もう1つの可能性として、所有しているスケジューラが非アクティブ化されているハードウェアスレッド上のすべての仮想プロセッサルートから、リソースが一時的に他のスケジューラに割り当てられていない可能性もあります。

ハードウェアスレッドのサブスクリプションレベルは、そのハードウェアスレッドに関連付けられている、サブスクライブしているスレッドとアクティブ化された仮想プロセッサのルートの数によって示されます。 特定のスケジューラの観点から見ると、ハードウェアスレッドの外部サブスクリプションレベルは、他のスケジューラが貢献するサブスクリプションの部分です。 リソースが外部でビジー状態になっていることを示す通知は、ハードウェアスレッドの外部サブスクリプションレベルが前の正の値からゼロになるとスケジューラに送信されます。

このメソッドによる通知は、ポリシーキーの値がポリシーキーの値と同じポリシーを持つスケジューラにのみ送信され `MinConcurrency` `MaxConcurrency` ます。 Scheduler ポリシーの詳細については、「スケジューラ [ポリシー](schedulerpolicy-class.md)」を参照してください。

通知を受け取るスケジューラは、作成時に初期通知のセットを取得し、それが割り当てられたリソースが外部でビジー状態かアイドル状態かを通知します。

## <a name="ischedulerremovevirtualprocessors-method"></a><a name="removevirtualprocessors"></a> IScheduler:: RemoveVirtualProcessors メソッド

以前にこのスケジューラに割り当てられた仮想プロセッサルートの削除を開始します。

```cpp
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*ppVirtualProcessorRoots*<br/>
`IVirtualProcessorRoot`削除する仮想プロセッサルートを表すインターフェイスの配列。

*count*<br/>
`IVirtualProcessorRoot`配列内のインターフェイスの数。

### <a name="remarks"></a>解説

リソースマネージャーは、メソッドを呼び出して、 `RemoveVirtualProcessors` スケジューラから一連の仮想プロセッサルートを取得します。 スケジューラは、仮想プロセッサルートで実行されたときに、各インターフェイスで [Remove](iexecutionresource-structure.md#remove) メソッドを呼び出すことが想定されています。 メソッドを呼び出した後は、インターフェイスを使用しないでください `IVirtualProcessorRoot` `Remove` 。

パラメーターは、 `ppVirtualProcessorRoots` インターフェイスの配列を指します。 削除する一連の仮想プロセッサルートの中で、メソッドを使用してすぐにルートがアクティブになることはありません `Remove` 。 アクティブ化され、作業を実行している、または非アクティブ化され、作業が到着するのを待機しているルートは、非同期的に返される必要があります。 スケジューラは、仮想プロセッサルートをできるだけ早く削除しようとする必要があります。 仮想プロセッサルートの削除を遅らせていると、スケジューラ内で、意図しないオーバーサブスクリプションが発生する可能性があります。

## <a name="ischedulerstatistics-method"></a><a name="statistics"></a> IScheduler:: Statistics メソッド

タスクの到着と完了率に関する情報を提供し、スケジューラのキューの長さを変更します。

```cpp
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```

### <a name="parameters"></a>パラメーター

*Ptask"レート"*<br/>
このメソッドの最後の呼び出し以降にスケジューラによって完了されたタスクの数。

*pTaskArrivalRate*<br/>
このメソッドの最後の呼び出し以降にスケジューラに到着したタスクの数。

*キューに登録された pnumberoftasksen*<br/>
すべてのスケジューラキュー内のタスクの合計数。

### <a name="remarks"></a>解説

このメソッドは、スケジューラの統計情報を収集するためにリソースマネージャーによって呼び出されます。 ここで収集された統計情報は、動的なフィードバックアルゴリズムを使用して、スケジューラにより多くのリソースを割り当て、リソースをどこに配置するかを判断するために使用されます。 スケジューラによって提供される値はオプティミスティックにすることができ、現在のカウントを正確に反映する必要があるとは限りません。

リソースマネージャーが、スケジューラとリソースマネージャーに登録されている他のスケジューラとの間でリソースのバランスを取る方法を決定するために、タスクの到着といったフィードバックを使用する場合は、このメソッドを実装する必要があります。 統計情報を収集しないことを選択した場合は、 `DynamicProgressFeedback` scheduler のポリシーの値にポリシーキーを設定でき `DynamicProgressFeedbackDisabled` ます。このメソッドは、リソースマネージャーによってスケジューラで呼び出されません。

統計情報がない場合、Resource Manager はハードウェアスレッドサブスクリプションレベルを使用して、リソースの割り当てと移行に関する決定を行います。 サブスクリプションレベルの詳細については、「 [Iexecutionresource:: CurrentSubscriptionLevel](iexecutionresource-structure.md#currentsubscriptionlevel)」を参照してください。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[スケジューラポリシークラス](schedulerpolicy-class.md)<br/>
[IExecutionContext 構造体](iexecutioncontext-structure.md)<br/>
[IThreadProxy 構造体](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager 構造体](iresourcemanager-structure.md)
