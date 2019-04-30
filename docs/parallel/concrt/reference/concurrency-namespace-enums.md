---
title: 同時実行の名前空間列挙型
ms.date: 11/04/2016
f1_keywords:
- CONCRT/concurrency::Agents_EventType
- CONCRT/concurrency::Concrt_TraceFlags
- CONCRT/concurrency::CriticalRegionType
- CONCRT/concurrency::PolicyElementKey
- CONCRT/concurrency::SchedulerType
- CONCRT/concurrency::SwitchingProxyState
- CONCRT/concurrency::WinRTInitializationType
- CONCRT/concurrency::join_type
- CONCRT/concurrency::message_status Enumeration
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
ms.openlocfilehash: d3eb49cd1555f23cc83efb0d8d912998295b3c55
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62337610"
---
# <a name="concurrency-namespace-enums"></a>同時実行の名前空間列挙型

||||
|-|-|-|
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|
|[CriticalRegionType](#criticalregiontype)|[DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)|[PolicyElementKey](#policyelementkey)|
|[SchedulerType](#schedulertype)|[SchedulingProtocolType](#schedulingprotocoltype)|[SwitchingProxyState](#switchingproxystate)|
|[WinRTInitializationType](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|
|[message_status](#message_status)|[task_group_status](#task_group_status)|

##  <a name="agent_status"></a>  agent_status 列挙体

`agent` の有効な状態。

```
enum agent_status;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`agent_canceled`|`agent` は取り消されました。|
|`agent_created`|`agent`は作成しますが、開始されていません。|
|`agent_done`|`agent`キャンセル中に完了しました。|
|`agent_runnable`|`agent`開始されましたが入力されていないその`run`メソッド。|
|`agent_started`|`agent`が開始します。|

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。[非同期エージェント](../../../parallel/concrt/asynchronous-agents.md)します。

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

##  <a name="agents_eventtype"></a>  Agents_EventType 列挙型

エージェント ライブラリによって提供されるトレース機能を使用してトレースできるイベントの種類。

```
enum Agents_EventType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`AGENTS_EVENT_CREATE`|オブジェクトの作成を表すイベントの種類|
|`AGENTS_EVENT_DESTROY`|イベントの種類を表すオブジェクトの削除|
|`AGENTS_EVENT_END`|いくつかの結論を表すイベントの種類の処理|
|`AGENTS_EVENT_LINK`|メッセージ ブロックのリンクを表すイベントの種類|
|`AGENTS_EVENT_NAME`|オブジェクトの名前を表すイベントの種類|
|`AGENTS_EVENT_SCHEDULE`|プロセスのスケジュールを表すイベントの種類|
|`AGENTS_EVENT_START`|いくつかの開始を表すイベントの種類の処理|
|`AGENTS_EVENT_UNLINK`|メッセージ ブロックの解除を表すイベントの種類|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

##  <a name="concrt_eventtype"></a>  ConcRT_EventType 列挙体

同時実行ランタイムによって提供されるトレース機能を使用してトレースできるイベントの種類。

```
enum ConcRT_EventType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`CONCRT_EVENT_ATTACH`|スケジューラへのアタッチの動作を表すイベントの種類。|
|`CONCRT_EVENT_BLOCK`|コンテキストのブロック動作を表すイベントの種類。|
|`CONCRT_EVENT_DETACH`|スケジューラからのデタッチの動作を表すイベントの種類。|
|`CONCRT_EVENT_END`|開始/終了イベントのペアの開始をマークするイベントの種類。|
|`CONCRT_EVENT_GENERIC`|その他のイベントに使用されるイベントの種類。|
|`CONCRT_EVENT_IDLE`|アイドル状態になるコンテキストの動作を表すイベントの種類。|
|`CONCRT_EVENT_START`|開始/終了イベントのペアの開始をマークするイベントの種類。|
|`CONCRT_EVENT_UNBLOCK`|コンテキストのブロック解除の動作を表すイベントの種類。|
|`CONCRT_EVENT_YIELD`|応答してコンテキストの動作を表すイベントの種類。|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h **Namespace:** 同時実行

##  <a name="concrt_traceflags"></a>  Concrt_TraceFlags 列挙型

イベントの種類のトレース フラグ。

```
enum Concrt_TraceFlags;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`AgentEventFlag`||
|`AllEventsFlag`||
|`ContextEventFlag`||
|`PPLEventFlag`||
|`ResourceManagerEventFlag`||
|`SchedulerEventFlag`||
|`VirtualProcessorEventFlag`||

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

##  <a name="criticalregiontype"></a>  CriticalRegionType 列挙型

コンテキストが存在するクリティカル領域の種類。

```
enum CriticalRegionType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`InsideCriticalRegion`|コンテキストがクリティカル領域内にあることを示します。 クリティカル領域内では、非同期の中断が、スケジューラからは見えません。 このような中断発生、スレッドが実行可能になるし、スケジューラをもう一度呼び出す代わりにそれを再開する Resource Manager が待機します。 このようなリージョン内で取得されたロックは、細心の注意で行われてする必要があります。|
|`InsideHyperCriticalRegion`|コンテキストがハイパー クリティカル領域内にあることを示します。 Hyper クリティカル領域内では、同期および非同期の中断が、スケジューラからは見えません。 このような一時的に停止する必要があります。 またはブロックが発生すると、リソース マネージャーがスレッドの実行可能になるし、スケジューラをもう一度呼び出す代わりにそれを再開を待機します。 このようなリージョン内で取得されるロックは、このようなリージョン外で実行されているコードと共有する必要があることはありません。 そうと、予測不可能なデッドロックが発生します。|
|`OutsideCriticalRegion`|コンテキストがクリティカル領域の外部にあることを示します。|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

##  <a name="dynamicprogressfeedbacktype"></a>  DynamicProgressFeedbackType 列挙体

`DynamicProgressFeedback` ポリシーによって使用され、スケジューラのリソースのバランスを再調整する際の判断基準として、スケジューラから収集された統計情報に従うか、または `Activate` インターフェイスの `Deactivate` メソッドおよび `IVirtualProcessorRoot` メソッドの呼び出しによってアイドル状態との間で状態が変化する仮想プロセッサのみに基づくかを示します。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)します。

```
enum DynamicProgressFeedbackType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`ProgressFeedbackDisabled`|スケジューラでは、進行状況に関する情報は収集しません。 再調整に基づいて行われます、基になるハードウェア スレッドのサブスクリプション レベルだけにします。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md)します。<br /><br /> この値は、使用するため、ランタイムによって予約されています。|
|`ProgressFeedbackEnabled`|スケジューラは、進行状況の情報を収集し、リソース マネージャーに渡されます。 リソース マネージャーでは、この統計情報を基になるハードウェア スレッドのサブスクリプション レベルだけでなく、スケジューラに代わってリソースを再調整を利用します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md)します。|

##  <a name="join_type"></a>  join_type 列挙体

`join` メッセージング ブロックの種類。

```
enum join_type;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`greedy`|最長一致`join`メッセージング ブロックが伝播時にメッセージをすぐにそのまま使用します。 これより効率的ですが、live - ロックでは、ネットワークの構成によって発生する可能性です。|
|`non_greedy`|非貪欲法による`join`メッセージング ブロック メッセージを延期し、すべてが到着した後、それらを使用します。 これらは確実に動作が遅くなります。|

### <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

##  <a name="message_status"></a>  message_status 列挙型

ブロックへの `message` オブジェクトの提供に対する有効な応答。

```
enum message_status;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`accepted`|ターゲットには、メッセージが受け入れられます。|
|`declined`|ターゲットがメッセージを受け入れませんでした。|
|`missed`|ターゲットが、メッセージの受け入れを試みましたが、使用できませんでした。|
|`postponed`|ターゲットは、メッセージを延期します。|

### <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

##  <a name="policyelementkey"></a>  PolicyElementKey 列挙体

ポリシー キーは、スケジューラの動作をさまざまな側面から表します。 各ポリシー要素は、キーと値の組み合わせで表現されます。 スケジューラのスケジューラ ポリシーとその影響に関する詳細については、次を参照してください。[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。

```
enum PolicyElementKey;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`ContextPriority`|スケジューラの各コンテキストのオペレーティング システムのスレッド優先順位。 このキーが値に設定されている場合`INHERIT_THREAD_PRIORITY`スケジューラのコンテキストは、スケジューラを作成したスレッドの優先順位を継承します。<br /><br /> 有効な値:Windows の有効な値のいずれかの`SetThreadPriority`関数、および特殊な値 `INHERIT_THREAD_PRIORITY`<br /><br /> 既定値: `THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|キロバイト単位で scheduler では、各コンテキストの予約済みのスタック サイズ。<br /><br /> 有効な値:正の整数<br /><br /> 既定値: `0`、スタック サイズのプロセスの既定値を使用することを示します。|
|`DynamicProgressFeedback`|スケジューラのリソースをスケジューラから収集された、または基になるハードウェア スレッドのサブスクリプション レベルに基づいてのみの統計情報に従って調整されるかどうかを判断します。 詳細については、次を参照してください。 [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)します。<br /><br /> 有効な値:メンバー、`DynamicProgressFeedbackType`列挙, か、`ProgressFeedbackEnabled`または `ProgressFeedbackDisabled`<br /><br /> 既定値: `ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|ときに、`SchedulingProtocol`ポリシー キーが値に設定されている`EnhanceScheduleGroupLocality`、仮想プロセッサのローカル キューごとにキャッシュできる実行可能なコンテキストの最大数を指定します。 このようなコンテキストは、後入れ先出し (LIFO) の順序を可能になる原因となった仮想プロセッサ上で通常実行されます。 このポリシーのキーはない場合、`SchedulingProtocol`キーが値に設定されている`EnhanceForwardProgress`します。<br /><br /> 有効な値:負でない整数<br /><br /> 既定値: `8`|
|`MaxConcurrency`|スケジューラによって必要なレベルの最大同時実行します。 リソース マネージャーは、最初にこのような多数の仮想プロセッサを割り当てるを試みます。 特殊な値[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)必要な同時実行レベルが、マシン上のハードウェア スレッドの数と同じであることを示します。 値が指定されている場合`MinConcurrency`がコンピューター上のハードウェア スレッドの数よりも大きいと`MaxConcurrency`として指定されて`MaxExecutionResources`の値は、`MaxConcurrency`が設定されているものと一致する発生`MinConcurrency`。<br /><br /> 有効な値:正の整数と特殊な値 `MaxExecutionResources`<br /><br /> 既定値: `MaxExecutionResources`|
|`MaxPolicyElementKey`|最大ポリシー要素のキー。 有効な要素キーではありません。|
|`MinConcurrency`|リソース マネージャーで、スケジューラに提供する必要があります最小同時実行レベルです。 スケジューラに割り当てられている仮想プロセッサの数は最小値を下回ることはありません。 特殊な値[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)最小同時実行レベルが、マシン上のハードウェア スレッドの数と同じであることを示します。 値が指定されている場合`MaxConcurrency`がコンピューター上のハードウェア スレッドの数より小さいと`MinConcurrency`として指定されて`MaxExecutionResources`の値は、`MinConcurrency`設定されているものと一致する値を下げた`MaxConcurrency`します。<br /><br /> 有効な値:負でない整数と特殊な値`MaxExecutionResources`します。 同時実行ランタイム スケジューラ、値の構築に使用されるスケジューラ ポリシーの`0`が無効です。<br /><br /> 既定値: `1`|
|`SchedulerKind`|実行コンテキストを基になるは、スケジューラを利用するスレッドの種類。 詳細については、次を参照してください。 [SchedulerType](#schedulertype)します。<br /><br /> 有効な値:メンバー、`SchedulerType`列挙型、たとえば、 `ThreadScheduler`<br /><br /> 既定値:`ThreadScheduler`します。 これは、すべてのオペレーティング システム上の Win32 スレッドに変換されます。|
|`SchedulingProtocol`|スケジューラによって使用されるスケジューリング アルゴリズムについて説明します。 詳細については、次を参照してください。 [SchedulingProtocolType](#schedulingprotocoltype)します。<br /><br /> 有効な値:メンバー、`SchedulingProtocolType`列挙, か、`EnhanceScheduleGroupLocality`または `EnhanceForwardProgress`<br /><br /> 既定値: `EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|一時的なハードウェア スレッドごとの仮想プロセッサ数。 ターゲットのオーバー サブスクリプション ファクター増やすことができます、リソース マネージャーによってを満たすために、必要に応じて`MaxConcurrency`マシン上のハードウェア スレッドにします。<br /><br /> 有効な値:正の整数<br /><br /> 既定値: `1`|
|`WinRTInitialization`||

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

##  <a name="schedulertype"></a>  SchedulerType 列挙型

基になる実行コンテキスト用にスケジューラが利用するスレッドの種類を示すために、`SchedulerKind` ポリシーにより使用されます。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)します。

```
enum SchedulerType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`ThreadScheduler`|通常の Win32 スレッドの明示的な要求を示します。|
|`UmsThreadDefault`|ユーザー モード スケジュール可能 (UMS) スレッドは、Visual Studio 2013 での同時実行ランタイムでサポートされていません。 `UmsThreadDefault` ポリシーの値として `SchedulerType` を使用しても、エラーは発生しません。 ただし、そのポリシーで作成されたスケジューラでは、既定で Win32 スレッドが使用されます。|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

##  <a name="schedulingprotocoltype"></a>  SchedulingProtocolType 列挙体

スケジューラに使用されるスケジューリング アルゴリズムを記述するために、`SchedulingProtocol` ポリシーによって使用されます。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)します。

```
enum SchedulingProtocolType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`EnhanceForwardProgress`|各タスクを実行した後、ラウンドロビン スケジュール グループを使用するスケジューラします。 ブロックされていないコンテキストは、最初に先出し (法 FIFO) 方式で通常スケジュールされます。 仮想プロセッサは、ブロック解除のコンテキストをキャッシュしません。|
|`EnhanceScheduleGroupLocality`|スケジューラは別のスケジュール グループに移動する前に、現在のスケジュール グループ内のタスクで作業を続行します。 ブロックされていないコンテキストでは、仮想プロセッサあたりはキャッシュされ、それらのブロックを解除する仮想プロセッサによって、後入れ先出し (LIFO) の形式で通常にスケジュールされます。|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

##  <a name="switchingproxystate"></a>  SwitchingProxyState 列挙体

あるスレッド プロキシから別のスレッド プロキシへの協調的なコンテキスト切り替えを実行するときに、スレッド プロキシの状態を示すために使用します。

```
enum SwitchingProxyState;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`Blocking`|呼び出し元のスレッドが排他的に所有、呼び出し元によって後でもう一度実行していると、その他のアクションを実行するまでが協調的にブロックしていることを示します。|
|`Idle`|呼び出し元のスレッドが不要になったスケジューラによって、Resource Manager に返されることを示します。 ディスパッチされていたコンテキストは、リソース マネージャーを利用することはありません。|
|`Nesting`|呼び出し元のスレッドが子スケジューラの入れ子は、別のスケジューラにアタッチするために、呼び出し元が必要なことを示します。|

### <a name="remarks"></a>Remarks

型のパラメーター`SwitchingProxyState`メソッドに渡される`IThreadProxy::SwitchTo`に Resource Manager の呼び出しを行っているスレッド プロキシを処理する方法を指示します。

この型の使用方法の詳細については、次を参照してください。 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)します。

##  <a name="task_group_status"></a>  task_group_status 列挙型

`task_group` オブジェクトまたは `structured_task_group` オブジェクトの実行状態を示します。 この型の値は、タスク グループに対してスケジュールされたタスクが完了するのを待機している多数のメソッドによって返されます。

```
enum task_group_status;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`canceled`|`task_group` オブジェクトまたは `structured_task_group` オブジェクトは取り消されました。 1 つまたは複数のタスクが実行されていない可能性があります。|
|`completed`|`task_group` オブジェクトまたは `structured_task_group` オブジェクトのキューに格納されたタスクは、正常に完了しました。|
|`not_complete`|`task_group` オブジェクトのキューに格納されたタスクは完了していません。 この値は、同時実行ランタイムによって現在返されていないことに注意してください。|

### <a name="requirements"></a>必要条件

**ヘッダー:** pplinterface.h

##  <a name="winrtinitializationtype"></a>  WinRTInitializationType 列挙型

`WinRTInitialization` ポリシーによって使用され、Windows 8 以上のオペレーティング システムで実行されるアプリケーション用のスケジューラ スレッドで、Windows ランタイムを初期化するかどうか、またどのように初期化するかを表します。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)します。

```
enum WinRTInitializationType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`DoNotInitializeWinRT`|アプリケーションが Windows 8 またはそれ以降のバージョンのオペレーティング システムで実行される場合、スケジューラ内のスレッドは、Windows ランタイムを初期化しません。|
|`InitializeWinRTAsMTA`|アプリケーションが Windows 8 またはそれ以降のバージョンのオペレーティング システムで実行される場合、スケジューラ内の各スレッドは、Windows ランタイムを初期化し、マルチスレッド アパートメントの一部であることを宣言します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
