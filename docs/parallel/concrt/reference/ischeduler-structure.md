---
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
ms.openlocfilehash: ccd82b5c5112bc322717f2b58d79d4c8f34f5bbd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368167"
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
|[Iスケジューラ::仮想プロセッサの追加](#addvirtualprocessors)|使用する一連の仮想プロセッサ ルートをスケジューラに提供します。 各`IVirtualProcessorRoot`インターフェイスは、スケジューラの代わりに作業を実行できる単一のスレッドを実行する権限を表します。|
|[I スケジューラ::取得ID](#getid)|スケジューラの一意の識別子を返します。|
|[Iスケジューラ::ゲットポリシー](#getpolicy)|スケジューラのポリシーのコピーを返します。 スケジューラ ポリシーの詳細については、「[スケジューラ ポリシー](schedulerpolicy-class.md)」を参照してください。|
|[Iスケジューラ::リソース外部にビジー](#notifyresourcesexternallybusy)|配列`ppVirtualProcessorRoots`内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドが、現在他のスケジューラによって使用されていることをスケジューラに通知します。|
|[Iスケジューラ::リソース外部にアイドル](#notifyresourcesexternallyidle)|配列`ppVirtualProcessorRoots`内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドが、他のスケジューラによって使用されないことをこのスケジューラに通知します。|
|[Iスケジューラ::仮想プロセッサの削除](#removevirtualprocessors)|このスケジューラに以前に割り当てられた仮想プロセッサ ルートの削除を開始します。|
|[Iスケジューラ::統計](#statistics)|タスクの到着率と完了率、およびスケジューラのキューの長さの変更に関連する情報を提供します。|

## <a name="remarks"></a>解説

Resource Manager と通信するカスタム スケジューラを実装する場合は、インターフェイスの実装を提供する`IScheduler`必要があります。 このインターフェイスは、スケジューラとリソース マネージャー間の双方向通信チャネルの一端です。 もう一方の端は、`IResourceManager`リソース`ISchedulerProxy`マネージャーによって実装されるインターフェイスとで表されます。

## <a name="inheritance-hierarchy"></a>継承階層

`IScheduler`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

**名前空間:** 同時実行

## <a name="ischeduleraddvirtualprocessors-method"></a><a name="addvirtualprocessors"></a>Iスケジューラ::追加仮想プロセッサメソッド

使用する一連の仮想プロセッサ ルートをスケジューラに提供します。 各`IVirtualProcessorRoot`インターフェイスは、スケジューラの代わりに作業を実行できる単一のスレッドを実行する権限を表します。

```cpp
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*プロセッサルート*<br/>
スケジューラに`IVirtualProcessorRoot`追加される仮想プロセッサ ルートを表すインターフェイスの配列。

*count*<br/>
配列内の`IVirtualProcessorRoot`インターフェイスの数。

### <a name="remarks"></a>解説

リソース マネージャーは、仮想`AddVirtualProcessor`プロセッサ ルートの初期セットをスケジューラに付与するメソッドを呼び出します。 また、スケジューラ間でリソースのバランスを再調整するときに、仮想プロセッサ ルートをスケジューラに追加するメソッドを呼び出すこともできます。

## <a name="ischedulergetid-method"></a><a name="getid"></a>I スケジューラ::GetId メソッド

スケジューラの一意の識別子を返します。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

一意の整数識別子。

### <a name="remarks"></a>解説

インターフェイスをリソース マネージャーによって提供されるメソッドのパラメーターとして使用する前に[、GetSchedulerId](concurrency-namespace-functions.md)関数を使用して、インターフェイスを`IScheduler`実装するオブジェクトの一意の識別子を取得する必要があります。 関数が呼び出されたときに、同じ識別子`GetId`を返す必要があります。

別のソースから取得した識別子は、未定義の動作を生じる可能性があります。

## <a name="ischedulergetpolicy-method"></a><a name="getpolicy"></a>Iスケジューラ::Getポリシーメソッド

スケジューラのポリシーのコピーを返します。 スケジューラ ポリシーの詳細については、「[スケジューラ ポリシー](schedulerpolicy-class.md)」を参照してください。

```cpp
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>戻り値

スケジューラのポリシーのコピー。

## <a name="ischedulernotifyresourcesexternallybusy-method"></a><a name="notifyresourcesexternallybusy"></a>Iスケジューラ::外部リソースの使用中のメソッド

配列`ppVirtualProcessorRoots`内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドが、現在他のスケジューラによって使用されていることをスケジューラに通知します。

```cpp
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*プロセッサルート*<br/>
他の`IVirtualProcessorRoot`スケジューラがビジー状態になっているハードウェア スレッドに関連付けられたインターフェイスの配列。

*count*<br/>
配列内の`IVirtualProcessorRoot`インターフェイスの数。

### <a name="remarks"></a>解説

特定のハードウェア スレッドを複数のスケジューラに同時に割り当てることが可能です。 この理由の 1 つは、リソースを共有せずに、すべてのスケジューラの最小同時実行を満たすだけのハードウェア スレッドがシステム上に存在しないことです。 別の可能性としては、所有しているスケジューラが他のスケジューラを使用していない場合、そのハードウェア スレッド上のすべての仮想プロセッサ ルートが非アクティブ化されている場合に、リソースが一時的に他のスケジューラに割り当てられる可能性があります。

ハードウェア スレッドのサブスクリプション レベルは、サブスクライブされたスレッドと、そのハードウェア スレッドに関連付けられているアクティブ化された仮想プロセッサ ルートの数で示されます。 特定のスケジューラの観点から見ると、ハードウェア スレッドの外部サブスクリプション レベルは、他のスケジューラが提供するサブスクリプションの一部です。 リソースが外部でビジーであるという通知は、ハードウェア スレッドの外部サブスクリプション レベルが 0 から正の領域に移行したときにスケジューラに送信されます。

このメソッドを使用した通知は、`MinConcurrency`ポリシー キーの値がポリシー キーの値と等しいポリシーを持つスケジューラにのみ`MaxConcurrency`送信されます。 スケジューラ ポリシーの詳細については、「[スケジューラ ポリシー](schedulerpolicy-class.md)」を参照してください。

通知の対象となるスケジューラは、割り当てられたリソースが外部でビジーであるかアイドルであるかを通知する、通知の作成時に一連の初期通知を受け取ります。

## <a name="ischedulernotifyresourcesexternallyidle-method"></a><a name="notifyresourcesexternallyidle"></a>メソッドを外部から通知します。

配列`ppVirtualProcessorRoots`内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドが、他のスケジューラによって使用されないことをこのスケジューラに通知します。

```cpp
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*プロセッサルート*<br/>
他の`IVirtualProcessorRoot`スケジューラがアイドル状態になったハードウェア スレッドに関連付けられたインターフェイスの配列。

*count*<br/>
配列内の`IVirtualProcessorRoot`インターフェイスの数。

### <a name="remarks"></a>解説

特定のハードウェア スレッドを複数のスケジューラに同時に割り当てることが可能です。 この理由の 1 つは、リソースを共有せずに、すべてのスケジューラの最小同時実行を満たすだけのハードウェア スレッドがシステム上に存在しないことです。 別の可能性としては、所有しているスケジューラが他のスケジューラを使用していない場合、そのハードウェア スレッド上のすべての仮想プロセッサ ルートが非アクティブ化されている場合に、リソースが一時的に他のスケジューラに割り当てられる可能性があります。

ハードウェア スレッドのサブスクリプション レベルは、サブスクライブされたスレッドと、そのハードウェア スレッドに関連付けられているアクティブ化された仮想プロセッサ ルートの数で示されます。 特定のスケジューラの観点から見ると、ハードウェア スレッドの外部サブスクリプション レベルは、他のスケジューラが提供するサブスクリプションの一部です。 リソースが外部でビジーであるという通知は、ハードウェア スレッドの外部サブスクリプション レベルが以前の正の値からゼロになるとスケジューラに送信されます。

このメソッドを使用した通知は、`MinConcurrency`ポリシー キーの値がポリシー キーの値と等しいポリシーを持つスケジューラにのみ`MaxConcurrency`送信されます。 スケジューラ ポリシーの詳細については、「[スケジューラ ポリシー](schedulerpolicy-class.md)」を参照してください。

通知の対象となるスケジューラは、割り当てられたリソースが外部でビジーであるかアイドルであるかを通知する、通知の作成時に一連の初期通知を受け取ります。

## <a name="ischedulerremovevirtualprocessors-method"></a><a name="removevirtualprocessors"></a>メソッドを削除します。

このスケジューラに以前に割り当てられた仮想プロセッサ ルートの削除を開始します。

```cpp
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*プロセッサルート*<br/>
削除する仮想`IVirtualProcessorRoot`プロセッサ ルートを表すインターフェイスの配列。

*count*<br/>
配列内の`IVirtualProcessorRoot`インターフェイスの数。

### <a name="remarks"></a>解説

リソース マネージャーは、スケジューラ`RemoveVirtualProcessors`から仮想プロセッサ ルートのセットを取り戻すメソッドを呼び出します。 スケジューラは、仮想プロセッサ ルートで完了すると、各インターフェイスで[Remove](iexecutionresource-structure.md#remove)メソッドを呼び出す必要があります。 インターフェイスでメソッドを`IVirtualProcessorRoot`呼び出した後は、`Remove`インターフェイスを使用しないでください。

パラメーター`ppVirtualProcessorRoots`は、インターフェイスの配列を指します。 削除する仮想プロセッサ ルートのセットの中で、ルートがアクティブ化されたことがないルートは、メソッドを`Remove`使用してすぐに返すことができます。 アクティブ化され、実行中の作業であるか、または非アクティブ化され、作業の到着を待機しているルートは、非同期的に返される必要があります。 スケジューラは、仮想プロセッサ ルートをできるだけ早く削除する試みを行う必要があります。 仮想プロセッサ ルートの削除を遅らせると、スケジューラ内で意図しないオーバーサブスクリプションが発生する可能性があります。

## <a name="ischedulerstatistics-method"></a><a name="statistics"></a>Iスケジューラ::統計方法

タスクの到着率と完了率、およびスケジューラのキューの長さの変更に関連する情報を提供します。

```cpp
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```

### <a name="parameters"></a>パラメーター

*タスク完了率*<br/>
このメソッドの最後の呼び出し以降にスケジューラによって完了したタスクの数。

*タスク到着率*<br/>
このメソッドの最後の呼び出し以降にスケジューラに到着したタスクの数。

*キューに入れられます。*<br/>
すべてのスケジューラ キュー内のタスクの合計数。

### <a name="remarks"></a>解説

このメソッドは、スケジューラの統計情報を収集するために、リソース マネージャーによって呼び出されます。 ここで収集される統計情報は、動的フィードバック アルゴリズムを駆動して、スケジューラにリソースを割り当てるのが適切なタイミングと、リソースを奪うタイミングを決定するために使用されます。 スケジューラによって提供される値は、楽観的であり、現在のカウントを正確に反映する必要はありません。

リソース マネージャーに登録されているスケジューラと他のスケジューラの間でリソースのバランスをとる方法を決定するタスクの到着などのフィードバックをリソース マネージャーに使用する場合は、このメソッドを実装する必要があります。 統計を収集しない場合は、スケジューラのポリシーの値`DynamicProgressFeedback``DynamicProgressFeedbackDisabled`にポリシー キーを設定できます。

統計情報がない場合、リソース マネージャーはハードウェア スレッド サブスクリプション レベルを使用して、リソースの割り当てと移行を決定します。 サブスクリプション レベルの詳細については[、「IExecution リソース::現在のサブスクリプションレベル](iexecutionresource-structure.md#currentsubscriptionlevel)」を参照してください。

## <a name="see-also"></a>関連項目

[同時実行名前空間](concurrency-namespace.md)<br/>
[キー](concurrency-namespace-enums.md)<br/>
[SchedulerPolicy クラス](schedulerpolicy-class.md)<br/>
[IExecutionContext 構造体](iexecutioncontext-structure.md)<br/>
[IThreadProxy 構造体](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager 構造体](iresourcemanager-structure.md)
