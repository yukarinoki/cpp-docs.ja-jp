---
title: concurrency 名前空間の列挙型 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: a40e3b2d-ad21-4229-9880-2cfa84f7ab8f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 068aa89c10e92203ce0e826e3aaca101f4786cbb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="concurrency-namespace-enums"></a>concurrency 名前空間の列挙型
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
|`agent_created`|`agent`作成されましたが、開始されていません。|  
|`agent_done`|`agent`取り消されることは正常に完了します。|  
|`agent_runnable`|`agent`された開始されるが入力されていないその`run`メソッドです。|  
|`agent_started`|`agent`が開始します。|  

### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期エージェント](../../../parallel/concrt/asynchronous-agents.md)です。  

### <a name="requirements"></a>要件  
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
|`AGENTS_EVENT_UNLINK`|イベントの種類を表すメッセージ ブロックのリンクを解除します。|  

### <a name="requirements"></a>要件  
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
|`CONCRT_EVENT_BLOCK`|コンテキストのブロックの動作を表すイベントの種類。|  
|`CONCRT_EVENT_DETACH`|スケジューラからのデタッチの動作を表すイベントの種類。|  
|`CONCRT_EVENT_END`|開始/終了イベントのペアの開始をマークするイベントの種類。|  
|`CONCRT_EVENT_GENERIC`|その他のイベントに使用されるイベントの種類。|  
|`CONCRT_EVENT_IDLE`|アイドル状態になるコンテキストの動作を表すイベントの種類。|  
|`CONCRT_EVENT_START`|開始/終了イベントのペアの開始をマークするイベントの種類。|  
|`CONCRT_EVENT_UNBLOCK`|コンテキストのブロック解除の動作を表すイベントの種類。|  
|`CONCRT_EVENT_YIELD`|コンテキスト応答の動作を表すイベントの種類。|  
  
### <a name="requirements"></a>要件  
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

### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h

##  <a name="criticalregiontype"></a>  CriticalRegionType 列挙型  
 コンテキストが存在するクリティカル領域の種類。  
  
```
enum CriticalRegionType;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`InsideCriticalRegion`|コンテキストが重要な領域の内側にあることを示します。 重要な領域の内側にときは、スケジューラから非同期の中断は表示されません。 このような中断発生、リソース マネージャーが実行可能になるし、スケジューラをもう一度呼び出すのではなくそれを再開するスレッドの待機します。 このような領域内に取得されたロックは、細心の注意で撮影した必要があります。|  
|`InsideHyperCriticalRegion`|コンテキストがハイパー クリティカル領域の内側にあることを示します。 ハイパー クリティカル領域の内部同期および非同期の中断は、スケジューラから表示されません。 このような中断、またはブロックが発生すると、リソース マネージャーが実行可能になるし、スケジューラをもう一度呼び出すのではなくそれを再開するスレッドの待機します。 このような領域内に取得されるロックは、このような領域の外側で実行されているコードと共有することはありません必要があります。 そうと、予測不可能なデッドロックが発生します。|  
|`OutsideCriticalRegion`|コンテキストがクリティカル領域の外部にあることを示します。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h 

##  <a name="dynamicprogressfeedbacktype"></a>  DynamicProgressFeedbackType 列挙体  
 `DynamicProgressFeedback` ポリシーによって使用され、スケジューラのリソースのバランスを再調整する際の判断基準として、スケジューラから収集された統計情報に従うか、または `Activate` インターフェイスの `Deactivate` メソッドおよび `IVirtualProcessorRoot` メソッドの呼び出しによってアイドル状態との間で状態が変化する仮想プロセッサのみに基づくかを示します。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)です。  
  
```
enum DynamicProgressFeedbackType;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`ProgressFeedbackDisabled`|スケジューラでは、進行状況に関する情報は収集しません。 再均衡化はのみに基づいて行わ基になるハードウェア スレッドのサブスクリプション レベル。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md)です。<br /><br /> この値は、使用するため、ランタイムによって予約されています。|  
|`ProgressFeedbackEnabled`|スケジューラは、進行状況に関する情報を収集し、リソース マネージャーに渡します。 リソース マネージャーでは、この統計情報を基になるハードウェア スレッドのサブスクリプション レベルだけでなく、スケジューラの代わりにリソースを再度均衡化を利用します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](IExecutionResource-structure.md)です。|  
##  <a name="join_type"></a>  join_type 列挙体  
 `join` メッセージング ブロックの種類。  
  
```
enum join_type;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`greedy`|最長一致`join`メッセージング ブロックはすぐに伝達時にメッセージを受信します。 これがより効率的ですが、ライブのロックをネットワークの構成によって発生する可能性です。|  
|`non_greedy`|最短`join`メッセージング ブロックのメッセージを延期し、すべてに到着した後、それらを使用します。 これらは確実に動作が、速度が低下します。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  

##  <a name="message_status"></a>  message_status 列挙体  
 ブロックへの `message` オブジェクトの提供に対する有効な応答。  
  
```
enum message_status;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`accepted`|ターゲットは、メッセージを受け入れられます。|  
|`declined`|ターゲットは、メッセージを受け入れませんでした。|  
|`missed`|ターゲットは、メッセージを受信しようとしていますが、使用できませんでした。|  
|`postponed`|ターゲットは、メッセージを延期します。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  

##  <a name="policyelementkey"></a>  PolicyElementKey 列挙体  
 ポリシー キーは、スケジューラの動作をさまざまな側面から表します。 各ポリシー要素は、キーと値の組み合わせで表現されます。 スケジューラでのスケジューラ ポリシーとその影響に関する詳細については、次を参照してください。[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)です。  
  
```
enum PolicyElementKey;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`ContextPriority`|オペレーティング システム スレッドの優先度、スケジューラ内の各コンテキスト。 このキーが値に設定されている場合`INHERIT_THREAD_PRIORITY`スケジューラ コンテキストは、スケジューラを作成したスレッドの優先度を継承します。<br /><br /> 有効な値: Windows の有効な値のいずれかの`SetThreadPriority`関数と特殊な値 `INHERIT_THREAD_PRIORITY`<br /><br /> 既定値: `THREAD_PRIORITY_NORMAL`|  
|`ContextStackSize`|キロバイト単位でスケジューラの各コンテキストの予約済みのスタック サイズ。<br /><br /> 有効な値: 正の整数<br /><br /> 既定値: `0`、スタック サイズのプロセスの既定値が使用することを示すです。|  
|`DynamicProgressFeedback`|スケジューラのリソースが、スケジューラから収集された、または基になるハードウェア スレッドのサブスクリプション レベルに基づいてのみの統計情報に従う再分配されるかどうかを判断します。 詳細については、次を参照してください。 [DynamicProgressFeedbackType](#dynamicprogressfeedbacktype)です。<br /><br /> 有効な値: のメンバー、`DynamicProgressFeedbackType`列挙型か、`ProgressFeedbackEnabled`または `ProgressFeedbackDisabled`<br /><br /> 既定値: `ProgressFeedbackEnabled`|  
|`LocalContextCacheSize`|ときに、`SchedulingProtocol`ポリシー キーが値に設定されている`EnhanceScheduleGroupLocality`、ローカル キューの仮想プロセッサあたりにキャッシュできる実行可能なコンテキストの最大数を指定します。 このようなコンテキストは、発生したため、実行可能になる仮想プロセッサ上で最後先出し (LIFO) の順序で通常実行されます。 注このポリシー キーの意味、`SchedulingProtocol`キーが値に設定されている`EnhanceForwardProgress`です。<br /><br /> 有効な値: 正の整数<br /><br /> 既定値: `8`|  
|`MaxConcurrency`|スケジューラによって必要なレベルの最大同時実行します。 リソース マネージャーは、このような多数の仮想プロセッサを最初に割り当てを試みます。 特殊な値[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)必要な同時実行レベルがコンピューター上のハードウェア スレッドの数と同じであることを示します。 値が指定されている場合`MinConcurrency`コンピューター上のハードウェア スレッドの数よりも大きいと`MaxConcurrency`として指定された`MaxExecutionResources`の値は、`MaxConcurrency`に設定されている一致するようには、発生`MinConcurrency`です。<br /><br /> 有効な値: 正の整数と特殊な値 `MaxExecutionResources`<br /><br /> 既定値: `MaxExecutionResources`|  
|`MaxPolicyElementKey`|最大ポリシー要素キー。 有効な要素キーではありません。|  
|`MinConcurrency`|リソース マネージャーによってスケジューラに提供する必要があります、最小同時実行レベル。 スケジューラに割り当てられている仮想プロセッサの数は、最小値を下回ることはありません。 特殊な値[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)最小同時実行レベルがコンピューター上のハードウェア スレッドの数と同じであることを示します。 値が指定されている場合`MaxConcurrency`がコンピューター上のハードウェア スレッドの数よりも小さいと`MinConcurrency`として指定された`MaxExecutionResources`の値は、`MinConcurrency`に設定されている一致するように値を下げた`MaxConcurrency`です。<br /><br /> 有効な値: 正の整数と特殊な値`MaxExecutionResources`です。 同時実行ランタイム スケジューラ、値の構築のために使用されるスケジューラ ポリシーの`0`が無効です。<br /><br /> 既定値: `1`|  
|`SchedulerKind`|基になる実行コンテキスト用にスケジューラが利用できるスレッドの種類。 詳細については、次を参照してください。 [SchedulerType](#schedulertype)です。<br /><br /> 有効な値: のメンバー、`SchedulerType`列挙型、たとえば、 `ThreadScheduler`<br /><br /> 既定値:`ThreadScheduler`です。 これは、すべてのオペレーティング システムで Win32 スレッドに変換します。|  
|`SchedulingProtocol`|スケジューラによって使用されるスケジューリング アルゴリズムについて説明します。 詳細については、次を参照してください。 [SchedulingProtocolType](#schedulingprotocoltype)です。<br /><br /> 有効な値: のメンバー、`SchedulingProtocolType`列挙型か、`EnhanceScheduleGroupLocality`または `EnhanceForwardProgress`<br /><br /> 既定値: `EnhanceScheduleGroupLocality`|  
|`TargetOversubscriptionFactor`|暫定的なハードウェア スレッドあたりの仮想プロセッサ数です。 ターゲット オーバー サブスクリプション係数増やすことができます、リソース マネージャーで、必要に応じてに対応する`MaxConcurrency`コンピューター上のハードウェア スレッドにします。<br /><br /> 有効な値: 正の整数<br /><br /> 既定値: `1`|  
|`WinRTInitialization`||  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  

##  <a name="schedulertype"></a>  SchedulerType 列挙体  
 基になる実行コンテキスト用にスケジューラが利用するスレッドの種類を示すために、`SchedulerKind` ポリシーにより使用されます。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)です。  
  
```
enum SchedulerType;
``` 

### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`ThreadScheduler`|通常の Win32 スレッドの明示的な要求を示します。|  
|`UmsThreadDefault`|Visual Studio 2013 での同時実行ランタイムでは、ユーザー モード スケジュール可能 (UMS) スレッドはサポートされていません。 `UmsThreadDefault` ポリシーの値として `SchedulerType` を使用しても、エラーは発生しません。 ただし、そのポリシーで作成されたスケジューラでは、既定で Win32 スレッドが使用されます。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
##  <a name="schedulingprotocoltype"></a>  SchedulingProtocolType 列挙体  
 スケジューラに使用されるスケジューリング アルゴリズムを記述するために、`SchedulingProtocol` ポリシーによって使用されます。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)です。  
  
```
enum SchedulingProtocolType;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`EnhanceForwardProgress`|スケジューラは、スケジュール グループ間のラウンド ロビンを各タスクを実行した後です。 ブロックされていないコンテキストは一般的最初先出し (FIFO) 方式でスケジュールを設定します。 仮想プロセッサは、ブロックされていないコンテキストをキャッシュしません。|  
|`EnhanceScheduleGroupLocality`|スケジューラは、別のスケジュール グループに移動する前に、現在のスケジュール グループ内のタスクの作業を続行します。 ブロックされていないコンテキストでは、仮想プロセッサあたりはキャッシュされ、それらのブロックを解除した仮想プロセッサでは通常最後先出し (LIFO) 方式でスケジュールされています。|  
  
### <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
 
##  <a name="switchingproxystate"></a>  SwitchingProxyState 列挙体  
 あるスレッド プロキシから別のスレッド プロキシへの協調的なコンテキスト切り替えを実行するときに、スレッド プロキシの状態を示すために使用します。  
  
```
enum SwitchingProxyState;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`Blocking`|呼び出し元のスレッドが排他的に所有、呼び出し元によって後でもう一度実行していると、その他のアクションを実行するまでは協調的ブロッキングことを示します。|  
|`Idle`|呼び出し元のスレッドが不要になったスケジューラによって、リソース マネージャーに返されることを示します。 ディスパッチされていたコンテキストは、リソース マネージャーでを利用することはありません。|  
|`Nesting`|呼び出し元のスレッドが子スケジューラの入れ子が、別のスケジューラにアタッチするために、呼び出し元が必要なことを示します。|  

### <a name="remarks"></a>コメント  
 型のパラメーター`SwitchingProxyState`メソッドに渡された`IThreadProxy::SwitchTo`に呼び出しを行っているスレッド プロキシを処理する方法をリソース マネージャーに指示します。  
  
 この型の使用方法の詳細については、次を参照してください。 [ithreadproxy::switchto](ithreadproxy-structure.md#switchto)です。  
  
##  <a name="task_group_status"></a>  task_group_status 列挙体  
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
  
### <a name="requirements"></a>要件  
 **ヘッダー:** pplinterface.h  

##  <a name="winrtinitializationtype"></a>  WinRTInitializationType 列挙型  
 `WinRTInitialization` ポリシーによって使用され、Windows 8 以上のオペレーティング システムで実行されるアプリケーション用のスケジューラ スレッドで、Windows ランタイムを初期化するかどうか、またどのように初期化するかを表します。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md)です。  
  
```
enum WinRTInitializationType;
```  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`DoNotInitializeWinRT`|アプリケーションが Windows 8 またはそれ以降のバージョンのオペレーティング システムで実行される場合、スケジューラ内のスレッドは、Windows ランタイムを初期化しません。|  
|`InitializeWinRTAsMTA`|アプリケーションが Windows 8 またはそれ以降のバージョンのオペレーティング システムで実行される場合、スケジューラ内の各スレッドは、Windows ランタイムを初期化し、マルチスレッド アパートメントの一部であることを宣言します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  

## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
