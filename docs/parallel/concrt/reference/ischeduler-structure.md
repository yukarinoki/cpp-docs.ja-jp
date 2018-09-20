---
title: IScheduler 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- IScheduler structure
ms.assetid: 471de85a-2b1a-4b6d-ab81-2eff2737161e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c926589165cbf93bd517612514bc27c88f28e15
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378866"
---
# <a name="ischeduler-structure"></a>IScheduler 構造体

作業スケジューラの抽象化のインターフェイスです。 同時実行ランタイムのリソース マネージャーは、このインターフェイスを使用して作業スケジューラと通信します。

## <a name="syntax"></a>構文

```
struct IScheduler;
```

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[IScheduler::AddVirtualProcessors](#addvirtualprocessors)|使用するための一連の仮想プロセッサ ルートのスケジューラを提供します。 各`IVirtualProcessorRoot`インターフェイスは、スケジューラのための作業を実行できる 1 つのスレッドを実行する権限を表します。|
|[IScheduler::GetId](#getid)|スケジューラの一意識別子を返します。|
|[IScheduler::GetPolicy](#getpolicy)|スケジューラのポリシーのコピーを返します。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)します。|
|[Ischeduler::notifyresourcesexternallybusy](#notifyresourcesexternallybusy)|この配列内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドをスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されているようになりました。|
|[IScheduler::NotifyResourcesExternallyIdle](#notifyresourcesexternallyidle)|この配列内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドをスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されていません。|
|[IScheduler::RemoveVirtualProcessors](#removevirtualprocessors)|このスケジューラに以前割り当てられた仮想プロセッサ ルートの削除を開始します。|
|[IScheduler::Statistics](#statistics)|タスクの到着から完了率、およびスケジューラのキューの長さの変更に関連する情報を提供します。|

## <a name="remarks"></a>Remarks

Resource Manager での通信を行うカスタム スケジューラを実装する場合は、実装を提供する必要があります、`IScheduler`インターフェイス。 このインターフェイスは、スケジューラとリソース マネージャー間の通信の双方向チャネルの片端となります。 もう一方の end がによって表される、`IResourceManager`と`ISchedulerProxy`リソース マネージャーでは実装されているインターフェイス。

## <a name="inheritance-hierarchy"></a>継承階層

`IScheduler`

## <a name="requirements"></a>要件

**ヘッダー:** concrtrm.h

**名前空間:** concurrency

##  <a name="addvirtualprocessors"></a>  Ischeduler::addvirtualprocessors メソッド

使用するための一連の仮想プロセッサ ルートのスケジューラを提供します。 各`IVirtualProcessorRoot`インターフェイスは、スケジューラのための作業を実行できる 1 つのスレッドを実行する権限を表します。

```
virtual void AddVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*ppVirtualProcessorRoots*<br/>
配列の`IVirtualProcessorRoot`スケジューラに追加されている仮想プロセッサを表すインターフェイスのルートします。

*count*<br/>
数`IVirtualProcessorRoot`配列内のインターフェイス。

### <a name="remarks"></a>Remarks

Resource Manager を呼び出す、`AddVirtualProcessor`スケジューラへの仮想プロセッサ ルートの初期セットを許可するメソッド。 スケジューラ間でリソースのバランスを再調整するときに、仮想プロセッサ ルートをスケジューラに追加するメソッドは呼び出すこともできます。

##  <a name="getid"></a>  Ischeduler::getid メソッド

スケジューラの一意識別子を返します。

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

一意の整数識別子。

### <a name="remarks"></a>Remarks

使用する必要があります、 [GetSchedulerId](concurrency-namespace-functions.md)を実装するオブジェクトの一意の識別子を取得する関数、`IScheduler`インターフェイス、メソッドのパラメーターとしてインターフェイスを使用する前に、リソース マネージャーでを指定します。 同じ識別子を返す予想されるときに、`GetId`関数が呼び出されます。

別のソースから取得した識別子は、未定義の動作になる可能性があります。

##  <a name="getpolicy"></a>  Ischeduler::getpolicy メソッド

スケジューラのポリシーのコピーを返します。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)します。

```
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>戻り値

スケジューラのポリシーのコピー。

##  <a name="notifyresourcesexternallybusy"></a>  Ischeduler::notifyresourcesexternallybusy メソッド

この配列内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドをスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されているようになりました。

```
virtual void NotifyResourcesExternallyBusy(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*ppVirtualProcessorRoots*<br/>
配列の`IVirtualProcessorRoot`を他のスケジューラはビジー状態にあるハードウェア スレッドに関連付けられているインターフェイス。

*count*<br/>
数`IVirtualProcessorRoot`配列内のインターフェイス。

### <a name="remarks"></a>Remarks

特定のハードウェア スレッドと同時に複数のスケジューラに割り当てられることができます。 この理由の 1 つがないことほど十分なハードウェア スレッド リソースを共有することがなく、他のすべてのスケジューラの最小の同時実行を満たすためにシステムの可能性があります。 別の方法としては、リソースが所有しているスケジューラを使用しない場合、そのハードウェア スレッドを非アクティブ化のすべての仮想プロセッサ ルートを使用して他のスケジューラに割り当てられる一時的です。

ハードウェア スレッドのサブスクリプション レベルでは、サブスクライブしているスレッドの数で表され、そのハードウェア スレッドに関連付けられた仮想プロセッサ ルートをアクティブ化します。 特定のスケジューラの観点からは、ハードウェア スレッドの外部のサブスクリプション レベルは、その他のスケジューラが関与するサブスクリプションの部分です。 ハードウェア スレッドの外部のサブスクリプション レベルが正の値にゼロから離れるときに、スケジューラにリソースが外部でビジー状態である通知が送信されます。

ポリシーを持つスケジューラにこのメソッドを使用して通知を送信のみ場所の値、`MinConcurrency`ポリシー キーがの値と等しい、`MaxConcurrency`ポリシー キー。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)します。

通知を修飾するスケジューラのセットを取得初期通知が作成されるときにだけに割り当てられているリソースがビジー状態かアイドル状態が外部でかどうかを示すことです。

##  <a name="notifyresourcesexternallyidle"></a>  Ischeduler::notifyresourcesexternallyidle メソッド

この配列内の仮想プロセッサ ルートのセットによって表されるハードウェア スレッドをスケジューラに通知`ppVirtualProcessorRoots`他のスケジューラによって使用されていません。

```
virtual void NotifyResourcesExternallyIdle(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*ppVirtualProcessorRoots*<br/>
配列の`IVirtualProcessorRoot`を他のスケジューラがアイドル状態になるハードウェア スレッドに関連付けられているインターフェイス。

*count*<br/>
数`IVirtualProcessorRoot`配列内のインターフェイス。

### <a name="remarks"></a>Remarks

特定のハードウェア スレッドと同時に複数のスケジューラに割り当てられることができます。 この理由の 1 つがないことほど十分なハードウェア スレッド リソースを共有することがなく、他のすべてのスケジューラの最小の同時実行を満たすためにシステムの可能性があります。 別の方法としては、リソースが所有しているスケジューラを使用しない場合、そのハードウェア スレッドを非アクティブ化のすべての仮想プロセッサ ルートを使用して他のスケジューラに割り当てられる一時的です。

ハードウェア スレッドのサブスクリプション レベルでは、サブスクライブしているスレッドの数で表され、そのハードウェア スレッドに関連付けられた仮想プロセッサ ルートをアクティブ化します。 特定のスケジューラの観点からは、ハードウェア スレッドの外部のサブスクリプション レベルは、その他のスケジューラが関与するサブスクリプションの部分です。 ハードウェア スレッドの外部のサブスクリプション レベルに前の正の値からゼロになった場合に、スケジューラにリソースが外部でビジー状態である通知が送信されます。

ポリシーを持つスケジューラにこのメソッドを使用して通知を送信のみ場所の値、`MinConcurrency`ポリシー キーがの値と等しい、`MaxConcurrency`ポリシー キー。 スケジューラ ポリシーの詳細については、次を参照してください。 [SchedulerPolicy](schedulerpolicy-class.md)します。

通知を修飾するスケジューラのセットを取得初期通知が作成されるときにだけに割り当てられているリソースがビジー状態かアイドル状態が外部でかどうかを示すことです。

##  <a name="removevirtualprocessors"></a>  Ischeduler::removevirtualprocessors メソッド

このスケジューラに以前割り当てられた仮想プロセッサ ルートの削除を開始します。

```
virtual void RemoveVirtualProcessors(
    _In_reads_(count) IVirtualProcessorRoot** ppVirtualProcessorRoots,
    unsigned int count) = 0;
```

### <a name="parameters"></a>パラメーター

*ppVirtualProcessorRoots*<br/>
配列の`IVirtualProcessorRoot`を削除する仮想プロセッサ ルートを表すインターフェイス。

*count*<br/>
数`IVirtualProcessorRoot`配列内のインターフェイス。

### <a name="remarks"></a>Remarks

Resource Manager を呼び出す、`RemoveVirtualProcessors`スケジューラからの一連の仮想プロセッサ ルートを実行するメソッド。 呼び出す、スケジューラが期待どおり、[削除](iexecutionresource-structure.md#remove)仮想プロセッサ ルートでは、その場合は、各インターフェイスのメソッド。 使用しないでください、`IVirtualProcessorRoot`インターフェイスの起動した後、`Remove`メソッド。

パラメーター`ppVirtualProcessorRoots`インターフェイスの配列を指します。 削除する仮想プロセッサ ルートのセット間で、ルートがアクティブ化されていないを使用してすぐに返される、`Remove`メソッド。 アクティブにしておくと、いずれかの処理を実行中または非アクティブ化されているし、処理の到着を待機しているルートは、非同期に返される必要があります。 スケジューラは、可能な限り早く仮想プロセッサ ルートを削除しようとするとすべてを行う必要があります。 仮想プロセッサ ルートの削除が遅れると、スケジューラ内でオーバー サブスクリプションを意図的でない可能性があります。

##  <a name="statistics"></a>  Ischeduler::statistics メソッド

タスクの到着から完了率、およびスケジューラのキューの長さの変更に関連する情報を提供します。

```
virtual void Statistics(
    _Out_ unsigned int* pTaskCompletionRate,
    _Out_ unsigned int* pTaskArrivalRate,
    _Out_ unsigned int* pNumberOfTasksEnqueued) = 0;
```

### <a name="parameters"></a>パラメーター

*pTaskCompletionRate*<br/>
このメソッドに最後の呼び出し以降に、スケジューラによって完了したタスクの数。

*pTaskArrivalRate*<br/>
このメソッドの最後の呼び出しが着信スケジューラのタスクの数。

*pNumberOfTasksEnqueued*<br/>
すべてのスケジューラ キュー内のタスクの合計数。

### <a name="remarks"></a>Remarks

このメソッドには、スケジューラの統計情報を収集するために、リソース マネージャーでは呼び出されます。 ここで収集された統計情報は、スケジューラにその他のリソースを割り当てるには適切な場合と、リソースをすぐに実行するタイミングを判断する動的なフィードバック アルゴリズムに使用されます。 スケジューラによって提供される値は、オプティミスティックを指定でき、現在の数を正確に反映する必ずしも必要はありません。

タスクの到着としてなどに関するフィードバックを使用して、スケジューラとリソース マネージャーに登録された他のスケジューラ間でリソースのバランスをとる方法を決定する Resource Manager の場合は、このメソッドを実装する必要があります。 統計情報を収集しないように選択する場合は、ポリシーのキーを設定できます`DynamicProgressFeedback`値`DynamicProgressFeedbackDisabled`マネージャーが、スケジューラでは、このメソッドを呼び出しませんスケジューラのポリシー、およびリソースにします。

統計情報がない場合は、Resource Manager は、リソース割り当てと移行に関する意思決定に、ハードウェア スレッドのサブスクリプション レベルを使用します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[SchedulerPolicy クラス](schedulerpolicy-class.md)<br/>
[IExecutionContext 構造体](iexecutioncontext-structure.md)<br/>
[IThreadProxy 構造体](ithreadproxy-structure.md)<br/>
[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)<br/>
[IResourceManager 構造体](iresourcemanager-structure.md)
