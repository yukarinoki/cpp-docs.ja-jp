---
title: コンカレンシー名前空間を持つ列挙型
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
ms.openlocfilehash: e3a943ed52ce9653086203713bb98331f809314d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372720"
---
# <a name="concurrency-namespace-enums"></a>コンカレンシー名前空間を持つ列挙型

||||
|-|-|-|
|[Agents_EventType](#agents_eventtype)|[ConcRT_EventType](#concrt_eventtype)|[Concrt_TraceFlags](#concrt_traceflags)|
|[クリティカルリージョンタイプ](#criticalregiontype)|[動的なプログレスフィードバックタイプ](#dynamicprogressfeedbacktype)|[キー](#policyelementkey)|
|[スケジューラタイプ](#schedulertype)|[プロトコルの種類のスケジューリング](#schedulingprotocoltype)|[スイッチングプロキシステート](#switchingproxystate)|
|[初期化タイプ](#winrtinitializationtype)|[agent_status](#agent_status)|[join_type](#join_type)|
|[message_status](#message_status)|[task_group_status](#task_group_status)|

## <a name="agent_status-enumeration"></a><a name="agent_status"></a>agent_status列挙

`agent` の有効な状態。

```cpp
enum agent_status;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`agent_canceled`|`agent` は取り消されました。|
|`agent_created`|作成`agent`されましたが、開始されていません。|
|`agent_done`|キャンセル`agent`されずに終了しました。|
|`agent_runnable`|は`agent`開始されましたが、メソッドには`run`入力されていません。|
|`agent_started`|が`agent`始まりました。|

### <a name="remarks"></a>解説

詳細については、「[非同期エージェント](../../../parallel/concrt/asynchronous-agents.md)」を参照してください。

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

## <a name="agents_eventtype-enumeration"></a><a name="agents_eventtype"></a>Agents_EventType列挙

エージェント ライブラリによって提供されるトレース機能を使用してトレースできるイベントの種類。

```cpp
enum Agents_EventType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`AGENTS_EVENT_CREATE`|オブジェクトの作成を表すイベントタイプ|
|`AGENTS_EVENT_DESTROY`|オブジェクトの削除を表すイベントタイプ|
|`AGENTS_EVENT_END`|何らかの処理の結論を表すイベントタイプ|
|`AGENTS_EVENT_LINK`|メッセージ ブロックのリンクを表すイベントタイプ|
|`AGENTS_EVENT_NAME`|オブジェクトの名前を表すイベントタイプ|
|`AGENTS_EVENT_SCHEDULE`|プロセスのスケジューリングを表すイベントタイプ|
|`AGENTS_EVENT_START`|一部の処理の開始を表すイベントタイプ|
|`AGENTS_EVENT_UNLINK`|メッセージ ブロックのリンク解除を表すイベント タイプ|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

## <a name="concrt_eventtype-enumeration"></a><a name="concrt_eventtype"></a>ConcRT_EventType列挙

コンカレンシー ランタイムによって提供されるトレース機能を使用してトレースできるイベントの種類。

```cpp
enum ConcRT_EventType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`CONCRT_EVENT_ATTACH`|スケジューラへのアタッチの動作を表すイベントの種類。|
|`CONCRT_EVENT_BLOCK`|コンテキスト ブロッキングの動作を表すイベントの種類。|
|`CONCRT_EVENT_DETACH`|スケジューラからのデタッチの動作を表すイベントの種類。|
|`CONCRT_EVENT_END`|開始/終了イベントのペアの開始を示すイベントの種類。|
|`CONCRT_EVENT_GENERIC`|その他のイベントに使用されるイベントの種類。|
|`CONCRT_EVENT_IDLE`|コンテキストがアイドル状態になる動作を表すイベントの種類。|
|`CONCRT_EVENT_START`|開始/終了イベントのペアの開始を示すイベントの種類。|
|`CONCRT_EVENT_UNBLOCK`|コンテキストのブロック解除の動作を表すイベントの種類。|
|`CONCRT_EVENT_YIELD`|コンテキスト生成の動作を表すイベントの種類。|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h**名前空間:** 同時実行

## <a name="concrt_traceflags-enumeration"></a><a name="concrt_traceflags"></a>Concrt_TraceFlags列挙

イベントの種類のトレース フラグ。

```cpp
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

## <a name="criticalregiontype-enumeration"></a><a name="criticalregiontype"></a>重要な領域型列挙体

コンテキストが存在するクリティカル領域の種類。

```cpp
enum CriticalRegionType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`InsideCriticalRegion`|コンテキストが重要な領域内であることを示します。 クリティカル領域内の場合、非同期の中断はスケジューラから非表示になります。 このような中断が発生した場合、リソース マネージャーはスレッドが実行可能になるのを待機し、スケジューラを再度呼び出す代わりにスレッドを再開します。 このような領域内で取得されたロックは、細心の注意を払って取る必要があります。|
|`InsideHyperCriticalRegion`|コンテキストがハイパー クリティカル領域内であることを示します。 ハイパークリティカル領域内で、同期および非同期の両方の中断がスケジューラから非表示になります。 このような中断またはブロックが発生した場合、リソース マネージャーはスレッドが実行可能になるまで待機し、スケジューラを再度呼び出す代わりに、スレッドを再開します。 このような領域内で取得されたロックは、このような領域の外部で実行されているコードと共有しないでください。 これを行うと、予期しないデッドロックが発生します。|
|`OutsideCriticalRegion`|コンテキストが重要な領域の外側であることを示します。|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrtrm.h

## <a name="dynamicprogressfeedbacktype-enumeration"></a><a name="dynamicprogressfeedbacktype"></a>列挙型の動的な進行状況

`DynamicProgressFeedback` ポリシーによって使用され、スケジューラのリソースのバランスを再調整する際の判断基準として、スケジューラから収集された統計情報に従うか、または `Activate` インターフェイスの `Deactivate` メソッドおよび `IVirtualProcessorRoot` メソッドの呼び出しによってアイドル状態との間で状態が変化する仮想プロセッサのみに基づくかを示します。 使用可能なスケジューラ ポリシーの詳細については、「 [PolicyElementKey](concurrency-namespace-enums.md)」を参照してください。

```cpp
enum DynamicProgressFeedbackType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`ProgressFeedbackDisabled`|スケジューラは進行状況情報を収集しません。 リバランスは、基になるハードウェア スレッドのサブスクリプション レベルのみに基づいて行われます。 サブスクリプション レベルの詳細については[、「IExecution リソース::現在のサブスクリプションレベル](IExecutionResource-structure.md)」を参照してください。<br /><br /> この値は、ランタイムが使用するために予約されています。|
|`ProgressFeedbackEnabled`|スケジューラーは、進捗状況情報を収集し、リソース・マネージャーに渡します。 リソース マネージャーは、基になるハードウェア スレッドのサブスクリプション レベルに加えて、スケジューラの代わりにリソースの再調整にこの統計情報を使用します。 サブスクリプション レベルの詳細については[、「IExecution リソース::現在のサブスクリプションレベル](IExecutionResource-structure.md)」を参照してください。|

## <a name="join_type-enumeration"></a><a name="join_type"></a>join_type列挙

`join` メッセージング ブロックの種類。

```cpp
enum join_type;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`greedy`|Greedy`join`メッセージング ブロックは、伝播時にメッセージを即座に受け入れます。 これは、より効率的ですが、ネットワークの設定によっては、ライブロックの可能性があります。|
|`non_greedy`|非貪欲な`join`メッセージング ブロックは、メッセージを延期し、すべてが到着した後にメッセージを使用しようとします。 これらは動作することが保証されていますが、遅くなります。|

### <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

## <a name="message_status-enumeration"></a><a name="message_status"></a>message_status列挙

ブロックへの `message` オブジェクトの提供に対する有効な応答。

```cpp
enum message_status;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`accepted`|ターゲットがメッセージを受け入れました。|
|`declined`|ターゲットはメッセージを受け入れなかった。|
|`missed`|ターゲットはメッセージを受け入れようとしましたが、使用できなくなりました。|
|`postponed`|ターゲットはメッセージを延期しました。|

### <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

## <a name="policyelementkey-enumeration"></a><a name="policyelementkey"></a>キーの列挙

ポリシー キーは、スケジューラの動作をさまざまな側面から表します。 各ポリシー要素は、キーと値の組み合わせで表現されます。 スケジューラ ポリシーとスケジューラに与える影響の詳細については、「[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)」を参照してください。

```cpp
enum PolicyElementKey;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`ContextPriority`|スケジューラ内の各コンテキストのオペレーティング システム スレッドの優先順位。 このキーが値`INHERIT_THREAD_PRIORITY`に設定されている場合、スケジューラのコンテキストは、スケジューラを作成したスレッドの優先順位を継承します。<br /><br /> 有効な値 : Windows`SetThreadPriority`関数の有効な値と特殊な値のいずれか`INHERIT_THREAD_PRIORITY`<br /><br /> デフォルト値 :`THREAD_PRIORITY_NORMAL`|
|`ContextStackSize`|スケジューラ内の各コンテキストの予約スタック サイズ (KB 単位)。<br /><br /> 有効な値 : 正の整数<br /><br /> デフォルト値`0`: : スタックサイズのプロセスのデフォルト値を使用することを示します。|
|`DynamicProgressFeedback`|スケジューラのリソースのバランスを、スケジューラから収集した統計情報に基づいて再調整するか、基になるハードウェア スレッドのサブスクリプション レベルのみに基づいて調整するかを決定します。 詳細については、「[動的な進行状況フィードバックの種類](#dynamicprogressfeedbacktype)」を参照してください。<br /><br /> 有効な値 : 列挙`DynamicProgressFeedbackType`体のメンバー `ProgressFeedbackEnabled` 、または列挙体のメンバー`ProgressFeedbackDisabled`<br /><br /> デフォルト値 :`ProgressFeedbackEnabled`|
|`LocalContextCacheSize`|ポリシー`SchedulingProtocol`キーが value`EnhanceScheduleGroupLocality`に設定されている場合、仮想プロセッサローカル キューごとにキャッシュできる実行可能なコンテキストの最大数を指定します。 このようなコンテキストは、通常、仮想プロセッサで実行可能になった先入れ先出し (LIFO) の順序で実行されます。 このポリシー キーは、 の値`SchedulingProtocol``EnhanceForwardProgress`に設定しても意味がありません。<br /><br /> 有効な値 : 負でない整数<br /><br /> デフォルト値 :`8`|
|`MaxConcurrency`|スケジューラが必要とする最大同時実行レベル。 リソース マネージャは、この数の仮想プロセッサを最初に割り当てようとします。 [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)の特殊な値は、必要な同時実行レベルがマシン上のハードウェア スレッドの数と同じであることを示します。 に`MinConcurrency`指定した値がマシン上のハードウェア・スレッドの数より大きく、`MaxConcurrency`として`MaxExecutionResources`指定されている場合、`MaxConcurrency`に設定されている値に一致するように`MinConcurrency`、 の値が発生します。<br /><br /> 有効な値 : 正の整数と特殊な値`MaxExecutionResources`<br /><br /> デフォルト値 :`MaxExecutionResources`|
|`MaxPolicyElementKey`|ポリシー要素の最大キー。 有効な要素キーではありません。|
|`MinConcurrency`|リソース マネージャーによってスケジューラに提供する必要がある最小同時実行レベル。 スケジューラに割り当てられた仮想プロセッサの数は、最小値を下回ることはありません。 [MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)の特殊値は、最小同時実行レベルがマシン上のハードウェア スレッドの数と同じであることを示します。 `MaxConcurrency`に指定した値がマシン`MinConcurrency`上のハードウェア・スレッドの数より少なく、 として`MaxExecutionResources`指定されている場合、`MinConcurrency`の値は、 に`MaxConcurrency`設定されているものと一致するように下げされます。<br /><br /> 有効な値 : 負でない整数と特殊な`MaxExecutionResources`値 。 同時実行ランタイム スケジューラの構築に使用されるスケジューラ ポリシーの場合、値`0`は無効であることに注意してください。<br /><br /> デフォルト値 :`1`|
|`SchedulerKind`|基になる実行コンテキストに対してスケジューラが使用するスレッドの型。 詳細については、「[スケジューラの種類](#schedulertype)」を参照してください。<br /><br /> 有効な値 :`SchedulerType`列挙のメンバー(`ThreadScheduler`<br /><br /> デフォルト値`ThreadScheduler`: これは、すべてのオペレーティング システム上の Win32 スレッドに変換されます。|
|`SchedulingProtocol`|スケジューラで使用されるスケジュール アルゴリズムについて説明します。 詳細については、「[スケジューリングプロトコルタイプ](#schedulingprotocoltype)」を参照してください。<br /><br /> 有効な値 : 列挙`SchedulingProtocolType`体のメンバー `EnhanceScheduleGroupLocality` 、または列挙体のメンバー`EnhanceForwardProgress`<br /><br /> デフォルト値 :`EnhanceScheduleGroupLocality`|
|`TargetOversubscriptionFactor`|ハードウェア スレッドごとの仮想プロセッサの仮数です。 ターゲットのオーバーサブスクリプション係数は、必要に応じて、マシン上のハードウェア スレッド`MaxConcurrency`を満たすために、リソース マネージャーによって増加できます。<br /><br /> 有効な値 : 正の整数<br /><br /> デフォルト値 :`1`|
|`WinRTInitialization`||

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

## <a name="schedulertype-enumeration"></a><a name="schedulertype"></a>スケジューラ型列挙

基になる実行コンテキスト用にスケジューラが利用するスレッドの種類を示すために、`SchedulerKind` ポリシーにより使用されます。 使用可能なスケジューラ ポリシーの詳細については、「 [PolicyElementKey](concurrency-namespace-enums.md)」を参照してください。

```cpp
enum SchedulerType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`ThreadScheduler`|通常の Win32 スレッドの明示的な要求を示します。|
|`UmsThreadDefault`|ユーザー モードの編集可能な (UMS) スレッドは、Visual Studio 2013 の同時実行ランタイムではサポートされていません。 `UmsThreadDefault` ポリシーの値として `SchedulerType` を使用しても、エラーは発生しません。 ただし、そのポリシーで作成されたスケジューラでは、既定で Win32 スレッドが使用されます。|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

## <a name="schedulingprotocoltype-enumeration"></a><a name="schedulingprotocoltype"></a>スケジューリングプロトコルタイプ列挙

スケジューラに使用されるスケジューリング アルゴリズムを記述するために、`SchedulingProtocol` ポリシーによって使用されます。 使用可能なスケジューラ ポリシーの詳細については、「 [PolicyElementKey](concurrency-namespace-enums.md)」を参照してください。

```cpp
enum SchedulingProtocolType;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`EnhanceForwardProgress`|スケジューラは、各タスクを実行した後にスケジュール グループをラウンドロビンすることを優先します。 ブロックされていないコンテキストは、通常、先入れ先出し (FIFO) の方法でスケジュールされます。 仮想プロセッサは、ブロックされていないコンテキストをキャッシュしません。|
|`EnhanceScheduleGroupLocality`|スケジューラは、別のスケジュール グループに移動する前に、現在のスケジュール グループ内のタスクを引き続き処理することを選択します。 ブロックされていないコンテキストは、仮想プロセッサごとにキャッシュされ、ブロックを解除した仮想プロセッサによって、通常は先入れ先出し (LIFO) の方法でスケジュールされます。|

### <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

## <a name="switchingproxystate-enumeration"></a><a name="switchingproxystate"></a>スイッチング プロキシステート列挙

あるスレッド プロキシから別のスレッド プロキシへの協調的なコンテキスト切り替えを実行するときに、スレッド プロキシの状態を示すために使用します。

```cpp
enum SwitchingProxyState;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`Blocking`|呼び出し元のスレッドが協調的にブロックされており、その後再度実行して他のアクションを実行するまで、呼び出し元が排他的に所有することを示します。|
|`Idle`|呼び出し元のスレッドがスケジューラで不要になり、リソース マネージャーに返されることを示します。 ディスパッチされていたコンテキストは、リソース マネージャーで使用できなくなりました。|
|`Nesting`|呼び出し元のスレッドが子スケジューラを入れ子にしており、別のスケジューラにアタッチするために呼び出し元が必要であることを示します。|

### <a name="remarks"></a>解説

メソッドに`SwitchingProxyState``IThreadProxy::SwitchTo`型のパラメーターが渡され、呼び出しを行うスレッド プロキシの処理方法をリソース マネージャーに指示します。

この型の使用方法の詳細については[、「IThreadProxy::SwitchTo](ithreadproxy-structure.md#switchto)」を参照してください。

## <a name="task_group_status-enumeration"></a><a name="task_group_status"></a>task_group_status列挙

`task_group` オブジェクトまたは `structured_task_group` オブジェクトの実行状態を示します。 この型の値は、タスク グループに対してスケジュールされたタスクが完了するのを待機している多数のメソッドによって返されます。

```cpp
enum task_group_status;
```

### <a name="values"></a>値

|名前|説明|
|----------|-----------------|
|`canceled`|`task_group` オブジェクトまたは `structured_task_group` オブジェクトは取り消されました。 1 つまたは複数のタスクが実行されていない可能性があります。|
|`completed`|`task_group` オブジェクトまたは `structured_task_group` オブジェクトのキューに格納されたタスクは、正常に完了しました。|
|`not_complete`|`task_group` オブジェクトのキューに格納されたタスクは完了していません。 この値は、コンカレンシー ランタイムによって現在返されていないことに注意してください。|

### <a name="requirements"></a>必要条件

**ヘッダー:** pplinterface.h

## <a name="winrtinitializationtype-enumeration"></a><a name="winrtinitializationtype"></a>列挙型

`WinRTInitialization` ポリシーによって使用され、Windows 8 以上のオペレーティング システムで実行されるアプリケーション用のスケジューラ スレッドで、Windows ランタイムを初期化するかどうか、またどのように初期化するかを表します。 使用可能なスケジューラ ポリシーの詳細については、「 [PolicyElementKey](concurrency-namespace-enums.md)」を参照してください。

```cpp
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

[同時実行名前空間](concurrency-namespace.md)
