---
title: concurrency 名前空間関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- concrt/concurrency::Alloc
- concrt/concurrency::DisableTracing
- concrt/concurrency::EnableTracing
- concrtrm/concurrency::GetExecutionContextId
- concrtrm/concurrency::GetOSVersion
- concrtrm/concurrency::GetProcessorNodeCount
- concrtrm/concurrency::GetSchedulerId
- agents/concurrency::asend
- ppltasks/concurrency::cancel_current_task
- ppltasks/concurrency::create_async
- ppltasks/concurrency::create_task
- concurrent_vector/concurrency::internal_assign_iterators
- ppl/concurrency::interruption_point
- agents/concurrency::make_choice
- agents/concurrency::make_greedy_join
- ppl/concurrency::make_task
- ppl/concurrency::parallel_buffered_sort
- ppl/concurrency::parallel_for_each
- ppl/concurrency::parallel_invoke
- ppl/concurrency::parallel_reduce
- ppl/concurrency::parallel_sort
- agents/concurrency::receive
- ppl/concurrency::run_with_cancellation_token
- pplconcrt/concurrency::set_ambient_scheduler
- concrt/concurrency::set_task_execution_resources
- ppltasks/concurrency::task_from_exception
- ppltasks/concurrency::task_from_result
- concrt/concurrency::wait
- ppltasks/concurrency::when_all
- ppltasks/concurrency::when_any
dev_langs:
- C++
ms.assetid: 520a6dff-9324-4df2-990d-302e3050af6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98e385f965ab3036d6ccf2383fd4ae6f420eb548
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2018
ms.locfileid: "42539486"
---
# <a name="concurrency-namespace-functions"></a>concurrency 名前空間関数
||||  
|-|-|-|  
|[Alloc](#alloc)|[CreateResourceManager](#createresourcemanager)|[DisableTracing](#disabletracing)|  
|[EnableTracing](#enabletracing)|[無料](#free)|[GetExecutionContextId](#getexecutioncontextid)|  
|[GetOSVersion](#getosversion)|[GetProcessorCount](#getprocessorcount)|[GetProcessorNodeCount](#getprocessornodecount)|  
|[GetSchedulerId](#getschedulerid)|[Trace_agents_register_name](#trace_agents_register_name)|[asend](#asend)|  
|[cancel_current_task](#cancel_current_task)|[clear](#clear)|[create_async](#create_async)|  
|[create_task](#create_task)|[get_ambient_scheduler](#get_ambient_scheduler)|[internal_assign_iterators](#internal_assign_iterators)|  
|[interruption_point](#interruption_point)|[is_current_task_group_canceling](#is_current_task_group_canceling)|[make_choice](#make_choice)|  
|[make_greedy_join](#make_greedy_join)|[make_join](#make_join)|[make_task](#make_task)|  
|[parallel_buffered_sort](#parallel_buffered_sort)|[parallel_for](#parallel_for)|[parallel_for_each](#parallel_for_each)|  
|[parallel_invoke](#parallel_invoke)|[parallel_radixsort](#parallel_radixsort)|[parallel_reduce](#parallel_reduce)|  
|[parallel_sort](#parallel_sort)|[parallel_transform](#parallel_transform)|[受信](#receive)|  
|[run_with_cancellation_token](#run_with_cancellation_token)|[send](#send)|[set_ambient_scheduler](#set_ambient_scheduler)|  
|[set_task_execution_resources](#set_task_execution_resources)|[swap](#swap)|[task_from_exception](#task_from_exception)|  
|[task_from_result](#task_from_result)|[try_receive](#try_receive)|[wait](#wait)|  
|[when_all](#when_all)|[when_any](#when_any)|  
  
##  <a name="alloc"></a>  Alloc  
 同時実行ランタイムのキャッシュ サブアロケータから、指定したサイズのメモリ ブロックを割り当てます。  
  
```
void* __cdecl Alloc(size_t _NumBytes);
```  
  
### <a name="parameters"></a>パラメーター  
 `_NumBytes`  
 割り当てるメモリのバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリへのポインター。  
  
### <a name="remarks"></a>Remarks  
 詳細については、のキャッシュ サブアロケータを使用してから得られるシナリオは、アプリケーションででしたを参照してください。[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。  
  
##  <a name="asend"></a>  asend  
 ターゲット ブロックにデータを反映するタスクをスケジュールする非同期送信操作です。  
  
```
template <class T>
bool asend(
    _Inout_ ITarget<T>* _Trg,
    const T& _Data);

template <class T>
bool asend(
    ITarget<T>& _Trg,
    const T& _Data);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 送信するデータの型。  
  
 `_Trg`  
 ポインターまたはデータが送信されるターゲットへの参照。  
  
 `_Data`  
 送信されるデータへの参照。  
  
### <a name="return-value"></a>戻り値  
 `true` メソッドが返される前に、メッセージが受け入れられた場合`false`それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。[メッセージを渡す関数](../../../parallel/concrt/message-passing-functions.md)します。  
  
##  <a name="cancel_current_task"></a>  cancel_current_task  
 現在実行中のタスクを取り消します。 この関数は、タスクの実行を中止して `canceled` 状態に遷移させるために、タスクの本体から呼び出すことができます。  
  
 `task` の本体以外では、この関数を呼び出すシナリオはサポートされません。 これを行うと、アプリケーションのクラッシュや停止など、定義されていない動作が発生します。  
  
```
inline __declspec(noreturn) void __cdecl cancel_current_task();
```  
  
##  <a name="clear"></a>  clear  
 破棄、同時実行のキューをクリアします。 現在のキューに格納された要素。 このメソッドは同時実行セーフではありません。  
  
```
template<typename T, class _Ax>
void concurrent_queue<T, _Ax>::clear();
```   
  
### <a name="parameters"></a>パラメーター  
 `T`  
 `_Ax`  
  
##  <a name="create_async"></a>  create_async  
 ユーザーが指定したラムダまたは関数オブジェクトに基づいて Windows ランタイムの非同期構造を作成します。 `create_async` の戻り値の型は、`IAsyncAction^`、`IAsyncActionWithProgress<TProgress>^`、`IAsyncOperation<TResult>^`、`IAsyncOperationWithProgress<TResult, TProgress>^` のいずれかで、メソッドに渡されるラムダのシグネチャに基づいています。  
  
```
template<typename _Function>
__declspec(noinline) auto create_async(const _Function& _Func)
    -> decltype(ref new details::_AsyncTaskGeneratorThunk<_Function>(_Func));
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 `_Func`  
 Windows ランタイムの非同期構造の作成元となるラムダまたは関数オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 IAsyncAction によって表される非同期構造 ^、IAsyncActionWithProgress\<TProgress > ^、IAsyncOperation\<TResult > ^、または IAsyncOperationWithProgress\<TResult, TProgress > ^ です。 返されるインターフェイスは、関数に渡されるラムダのシグネチャによって異なります。  
  
### <a name="remarks"></a>Remarks  
 ラムダの戻り値の型によって、構造がアクションであるか操作であるかが判別されます。  
  
 ラムダが void を返すと、アクションが作成されます。 ラムダが型 `TResult` の結果を返すと、TResult の操作が作成されます。  
  
 ラムダは `task<TResult>` を返すことがあります。この戻り値は、それ自体に非同期操作をカプセル化します。また、非同期操作を表すタスクのチェーンの継続として機能する場合もあります。 この場合、ラムダ自体はインラインで実行されます。これは、タスクが非同期的に実行されたタスクであり、ラムダの戻り値の型がラップ解除され `create_async` によって返される非同期構造を生成するためです。 つまり、あるラムダを返すタスク\<void > アクション、およびタスクを返すラムダを作成すると、\<TResult > TResult の操作の作成が発生します。  
  
 ラムダでは、引数を使用しない場合、または 1 つか 2 つの引数を使用する場合があります。 有効な引数は `progress_reporter<TProgress>` と `cancellation_token` です。これらを両方とも使用する場合は、この順序で指定してください。 ラムダで引数を使用しないと、進行状況の報告機能を持たない非同期構造が作成されます。 ラムダで progress_reporter\<TProgress > により`create_async`を毎回型 TProgress の進行状況を報告する非同期構造を返す、 `report` progress_reporter オブジェクトのメソッドが呼び出されます。 cancellation_token を使用するラムダでは、そのトークンを利用して取り消しを確認する場合があります。また、作成されるタスクにこのトークンを渡す場合もあります。これにより、非同期構造を取り消すと、それらのタスクも取り消されます。  
  
 ラムダまたは関数オブジェクトの本体が結果を返す場合 (task\<TResult >)、タスク、ランタイムのコンテキスト内の MTA が暗黙的に作成するプロセス内で、ラムダを非同期的に実行されます。 `IAsyncInfo::Cancel` のメソッドにより、暗黙のタスクが取り消されます。  
  
 ラムダの本体がタスクを返す場合、ラムダはインラインで実行されます。また、ラムダが型 `cancellation_token` の引数を使用するように宣言すると、タスクの作成時にこのトークンを渡すことによって、ラムダ内で作成されるタスクの取り消しをトリガーできます。 また、トークンに対して `register_callback` メソッドを使用すると、生成される非同期操作や非同期アクションで `IAsyncInfo::Cancel` を呼び出すときに、ランタイムでコールバックを呼び出すこともできます。  
  
 この関数では、Windows ランタイム アプリで使用できるのみです。  
  
##  <a name="createresourcemanager"></a>  CreateResourceManager  
 同時実行ランタイムのリソース マネージャーのシングルトン インスタンスを表すインターフェイスを返します。 リソース マネージャーは、相互の連携を必要とするスケジューラにリソースを割り当てます。  
  
```
IResourceManager* __cdecl CreateResourceManager();
```  
  
### <a name="return-value"></a>戻り値  
 `IResourceManager` インターフェイス。  
  
### <a name="remarks"></a>Remarks  
 それ以降、このメソッドを複数回呼び出すと、リソース マネージャーの同じインスタンスが返されます。 メソッドを呼び出すたびの参照は、Resource Manager でのカウントし、への呼び出しと一致する必要があります、 [iresourcemanager::release](http://msdn.microsoft.com/en-us/5d1356ec-fbd3-4284-a361-1e9e20bbb522)メソッド、スケジューラが完了すると、Resource Manager との通信。  
  
 [unsupported_os](unsupported-os-class.md)が、同時実行ランタイムによって、オペレーティング システムがサポートされていない場合にスローされます。  
  
##  <a name="create_task"></a>  create_task  
 作成、PPL[タスク](http://msdn.microsoft.com/en-us/5389e8a5-5038-40b6-844a-55e9b58ad35f)オブジェクト。 `create_task` は、タスク コンストラクターを使用した任意の場所で使用できます。 タスクの作成中に `auto` キーワードが使用できるようになるため、これは参考用として用意されています。  
  
```
template<typename T>
__declspec(noinline) auto create_task(T _Param, const task_options& _TaskOptions = task_options())
    -> task<typename details::_TaskTypeFromParam<T>::T>;

template<typename _ReturnType>
__declspec( noinline) task<_ReturnType> create_task(const task<_ReturnType>& _Task);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 パラメーターの型。これに基づいてタスクが構築されます。  
  
 `_ReturnType`  
 `_Param`  
 パラメーター。これに基づいてタスクが構築されます。 ラムダまたは関数オブジェクトでは、可能性があります、`task_completion_event`オブジェクト、別`task`オブジェクト、または UWP アプリでタスクを使用している場合::iasyncinfo インターフェイスをします。  
  
 `_TaskOptions`  
 `_Task`  
  
### <a name="return-value"></a>戻り値  
 型 `T` の新しいタスク。`_Param` から推論されます。  
  
### <a name="remarks"></a>Remarks  
 最初のオーバーロードは、単一のパラメーターを受け取るタスク コンストラクターのように動作します。  
  
 2 番目のオーバーロードは、新しく作成されたタスクで指定されたキャンセル トークンを関連付けます。 このオーバーロードを使用すると、最初のパラメーターとして別の `task` オブジェクトを渡すことができません。  
  
 返されたタスクの種類は、関数の最初のパラメーターから推測されます。 `_Param` が `task_completion_event<T>`、`task<T>`、または型 `T` か型 `task<T>` を返すファンクタの場合、作成されたタスクの型は `task<T>` です。  
  
 UWP アプリで場合`_Param`型:iasyncoperation\<T > ^ または Windows::Foundation::IAsyncOperationWithProgress\<T, P > ^、またはそれらの型のいずれかを返すファンクタの場合、作成されたタスクになります型`task<T>`します。 場合`_Param`型:iasyncaction ^ または Windows::Foundation::IAsyncActionWithProgress\<P > ^、またはそれらの型のいずれかを返すファンクタの場合、作成されたタスクは入力が`task<void>`します。  
  
##  <a name="disabletracing"></a>  DisableTracing  
 同時実行ランタイムでのトレースを無効にします。 この関数は、ETW トレースが既定で未登録であるため非推奨とされます。  
  
```
__declspec(deprecated("Concurrency::DisableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl DisableTracing();
```  
  
### <a name="return-value"></a>戻り値  
 トレースが正しく無効になっている場合`S_OK`が返されます。 トレースが開始されていませんが場合、`E_NOT_STARTED`が返されます  
  
##  <a name="enabletracing"></a>  EnableTracing  
 同時実行ランタイムでトレースを有効にします。 この関数は、ETW トレースが既定でオンであるため非推奨とされます。  
  
```
__declspec(deprecated("Concurrency::EnableTracing is a deprecated function.")) _CRTIMP HRESULT __cdecl EnableTracing();
```  
  
### <a name="return-value"></a>戻り値  
 トレースが開始された正しく場合`S_OK`が返されます。 それ以外の場合、`E_NOT_STARTED`が返されます。  
  
##  <a name="free"></a>  無料  
 以前に `Alloc` メソッドによって同時実行ランタイムのキャッシュ サブアロケータに割り当てられたメモリ ブロックを解放します。  
  
```
void __cdecl Free(_Pre_maybenull_ _Post_invalid_ void* _PAllocation);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PAllocation`  
 以前に `Alloc` メソッドによって割り当てられた解放するメモリへのポインター。 `_PAllocation` パラメーターの値が `NULL` に設定されている場合、このメソッドはそれを無視してすぐに制御を戻します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、のキャッシュ サブアロケータを使用してから得られるシナリオは、アプリケーションででしたを参照してください。[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。  
  
##  <a name="get_ambient_scheduler"></a>  get_ambient_scheduler  
  
```
inline std::shared_ptr<::Concurrency::scheduler_interface> get_ambient_scheduler();
```  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="getexecutioncontextid"></a>  GetExecutionContextId  
 `IExecutionContext` インターフェイスを実装する実行コンテキストに割り当てることのできる一意識別子を返します。  
  
```
unsigned int __cdecl GetExecutionContextId();
```  
  
### <a name="return-value"></a>戻り値  
 実行コンテキストの一意の識別子。  
  
### <a name="remarks"></a>Remarks  
 渡す前に、実行コンテキストの識別子を取得するには、このメソッドを使用して、`IExecutionContext`リソース マネージャーによって提供されるメソッドのいずれかのパラメーターとしてインターフェイス。  
  
##  <a name="getosversion"></a>  GetOSVersion  
 オペレーティング システムのバージョンを返します。  
  
```
IResourceManager::OSVersion __cdecl GetOSVersion();
```  
  
### <a name="return-value"></a>戻り値  
 オペレーティング システムを表す列挙値。  
  
### <a name="remarks"></a>Remarks  
 [unsupported_os](unsupported-os-class.md)が、同時実行ランタイムによって、オペレーティング システムがサポートされていない場合にスローされます。  
  
##  <a name="getprocessorcount"></a>  GetProcessorCount  
 基になるシステム上のハードウェア スレッドの数を返します。  
  
```
unsigned int __cdecl GetProcessorCount();
```  
  
### <a name="return-value"></a>戻り値  
 ハードウェア スレッドの数。  
  
### <a name="remarks"></a>Remarks  
 [unsupported_os](unsupported-os-class.md)が、同時実行ランタイムによって、オペレーティング システムがサポートされていない場合にスローされます。  
  
##  <a name="getprocessornodecount"></a>  GetProcessorNodeCount  
 基になるシステム上の NUMA ノードまたはプロセッサ パッケージの数を返します。  
  
```
unsigned int __cdecl GetProcessorNodeCount();
```  
  
### <a name="return-value"></a>戻り値  
 NUMA ノードまたはプロセッサ パッケージの数。  
  
### <a name="remarks"></a>Remarks  
 システムに含まれる NUMA ノードの数がプロセッサ パッケージの数より多い場合は、NUMA ノードの数が返されます。それ以外の場合は、プロセッサ パッケージの数が返されます。  
  
 [unsupported_os](unsupported-os-class.md)が、同時実行ランタイムによって、オペレーティング システムがサポートされていない場合にスローされます。  
  
##  <a name="getschedulerid"></a>  GetSchedulerId  
 `IScheduler` インターフェイスを実装するスケジューラに割り当てることができる一意識別子を返します。  
  
```
unsigned int __cdecl GetSchedulerId();
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラの一意の識別子。  
  
### <a name="remarks"></a>Remarks  
 渡す前に、スケジューラの識別子を取得するには、このメソッドを使用して、`IScheduler`リソース マネージャーによって提供されるメソッドのいずれかのパラメーターとしてインターフェイス。  
  
##  <a name="internal_assign_iterators"></a>  internal_assign_iterators  
  
```
template<typename T, class _Ax>
template<class _I> 
void concurrent_vector<T, _Ax>::internal_assign_iterators(
   _I first,
   _I last);
```   
  
### <a name="parameters"></a>パラメーター  
 `T`  
 `_Ax`  
 `_I`  
 `first`  
 `last`  
  
##  <a name="interruption_point"></a>  interruption_point  
 取り消しの割り込みポイントを作成します。 この関数が呼び出されるコンテキストで取り消しが進行中の場合、現在実行中の並列処理を中止する内部例外がスローされます。 取り消しが進行中でない場合は、何も実行されません。  
  
```
inline void interruption_point();
```  
  
### <a name="remarks"></a>Remarks  
 によってスローされた内部のキャンセルの例外をキャッチする必要があります、`interruption_point()`関数。 例外をキャッチして、ランタイムによって処理し、でキャッチ異常動作するプログラムが発生する可能性があります。  
  
##  <a name="is_current_task_group_canceling"></a>  is_current_task_group_canceling  
 現在のコンテキストで現在インラインで実行されているタスク グループがアクティブなキャンセル処理中である (または間もなくキャンセル処理が開始される) かどうかを示す値を返します。 現在のコンテキストで現在インラインで実行されているタスク グループが存在しない場合は、`false` が返されます。  
  
```
bool __cdecl is_current_task_group_canceling();
```  
  
### <a name="return-value"></a>戻り値  
 `true` 現在実行されているタスク グループをキャンセルすると場合、`false`それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。[キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)します。  
  
##  <a name="make_choice"></a>  make_choice  
 オプションの `choice` や `Scheduler`、および 2 つ以上の入力ソースから `ScheduleGroup` メッセージング ブロックを構築します。  
  
```
template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    Scheduler& _PScheduler,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    ScheduleGroup& _PScheduleGroup,
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
choice<std::tuple<T1, T2, Ts...>> make_choice(
    T1  _Item1,
    T2  _Item2,
    Ts... _Items);
```  
  
### <a name="parameters"></a>パラメーター  
 `T1`  
 1 番目のソースのメッセージ ブロックの型。  
  
 `T2`  
 2 番目のソースのメッセージ ブロックの型。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。  
  
 `_Item1`  
 1 番目のソース。  
  
 `_Item2`  
 2 番目のソース。  
  
 `_Items`  
 その他のソース。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `choice` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="return-value"></a>戻り値  
 2 個またはそれ以上の入力ソースを持つ `choice` メッセージ ブロック。  
  
##  <a name="make_greedy_join"></a>  make_greedy_join  
 オプションの `greedy multitype_join` や `Scheduler`、および 2 つ以上の入力ソースから `ScheduleGroup` メッセージング ブロックを構築します。  
  
```
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>,greedy> make_greedy_join(
    Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>, greedy> make_greedy_join(
    T1 _Item1,
    T2 _Items,
    Ts... _Items);
```  
  
### <a name="parameters"></a>パラメーター  
 `T1`  
 1 番目のソースのメッセージ ブロックの型。  
  
 `T2`  
 2 番目のソースのメッセージ ブロックの型。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。  
  
 `_Item1`  
 1 番目のソース。  
  
 `_Item2`  
 2 番目のソース。  
  
 `_Items`  
 その他のソース。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="return-value"></a>戻り値  
 2 個またはそれ以上の入力ソースを持つ `greedy multitype_join` メッセージ ブロック。  
  
##  <a name="make_join"></a>  make_join  
 オプションの `non_greedy multitype_join` や `Scheduler`、および 2 つ以上の入力ソースから `ScheduleGroup` メッセージング ブロックを構築します。  
  
```
template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> 
    make_join(
 Scheduler& _PScheduler,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
 ScheduleGroup& _PScheduleGroup,
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);

template<typename T1, typename T2, typename... Ts>
multitype_join<std::tuple<T1, T2, Ts...>> make_join(
    T1 _Item1,
    T2 _Item2,
    Ts... _Items);
```  
  
### <a name="parameters"></a>パラメーター  
 `T1`  
 1 番目のソースのメッセージ ブロックの型。  
  
 `T2`  
 2 番目のソースのメッセージ ブロックの型。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。  
  
 `_Item1`  
 1 番目のソース。  
  
 `_Item2`  
 2 番目のソース。  
  
 `_Items`  
 その他のソース。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `multitype_join` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="return-value"></a>戻り値  
 2 個またはそれ以上の入力ソースを持つ `non_greedy multitype_join` メッセージ ブロック。  
  
##  <a name="make_task"></a>  make_task  
 `task_handle` オブジェクトを作成するためのファクトリ メソッドです。  
  
```
template <class _Function>
task_handle<_Function> make_task(const _Function& _Func);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 によって表される作業を実行するときに呼び出される関数オブジェクトの種類、`task_handle`オブジェクト。  
  
 `_Func`  
 によって表される作業を実行するときに呼び出される関数、`task_handle`オブジェクト。 ラムダをファンクター、関数へのポインターがありますまたはシグネチャを持つ関数呼び出し演算子のバージョンをサポートする任意のオブジェクト`void operator()()`します。  
  
### <a name="return-value"></a>戻り値  
 `task_handle` オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 この関数は、作成する必要がある場合に便利です、`task_handle`ラムダ ファンクタの場合は true。 型を知らなくてもオブジェクトを作成できるため、ラムダ式では、オブジェクト。  
  
##  <a name="parallel_buffered_sort"></a>  parallel_buffered_sort  
 指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って、並列に配置します。 この関数は、比較ベースで不安定なインプレース並べ替えという点で `std::sort` と意味が同じです。ただし、`O(n)` 追加スペースが必要で、並べ替えている要素を既定で初期化する必要があります。  
  
```
template<typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator,
    typename _Random_iterator>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_buffered_sort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Random_iterator`  
 入力範囲の反復子の型。  
  
 `_Allocator`  
 C++ 標準ライブラリの互換性のあるメモリ アロケーターの型。  
  
 `_Function`  
 バイナリの比較子の型。  
  
 `_Begin`  
 並べ替えられる範囲内の最初の要素の位置を示すランダム アクセス反復子。  
  
 `_End`  
 並べ替えられる範囲内の最後の要素の 1 つ後ろの位置を示すランダム アクセス反復子。  
  
 `_Alloc`  
 C++ 標準ライブラリの互換性のあるメモリ アロケーターのインスタンス。  
  
 `_Func`  
 順序の一連の要素によって満たされるように比較の基準を定義するユーザー定義の述語関数オブジェクト。 二項述語は 2 つの引数を受け取り、条件が満たされている場合は `true`、満たされていない場合は `false` を返します。 この比較子関数は、シーケンスからの要素のペアで厳密弱順序を強制する必要があります。  
  
 `_Chunk_size`  
 並列実行用に 2 つに分割するチャンクの最小サイズ。  
  
### <a name="remarks"></a>Remarks  
 すべてのオーバー ロードを必要と`n * sizeof(T)`追加領域は、場所`n`が並べ替えられる要素の数と`T`要素の型は、します。 ほとんどの場合 parallel_buffered_sort は、経由でパフォーマンスの向上を表示、 [parallel_sort](concurrency-namespace-functions.md)、および使用可能なメモリがある場合は parallel_sort 経由で使用する必要があります。  
  
 二項比較演算子を指定しない場合`std::less`演算子を提供する要素の型を必要とすると、既定として使用されます`operator<()`します。  
  
 アロケーターの型またはインスタンスでは、C++ 標準ライブラリのメモリ アロケーターを指定しない場合`std::allocator<T>`バッファーを割り当てるために使用します。  
  
 アルゴリズムは入力範囲を 2 つのチャンクに分割し、連続して各チャンクを並列で実行するための 2 つのサブ チャンクに分割します。 省略可能な引数`_Chunk_size`サイズのチャンクを処理する必要がある、アルゴリズムに示すために使用できます <`_Chunk_size`逐次的にします。  
  
##  <a name="parallel_for"></a>  parallel_for  
 `parallel_for` は、一定の範囲のインデックスを反復処理し、各反復処理で、ユーザーが指定した関数を並列で実行します。  
  
```
template <typename _Index_type, typename _Function, typename _Partitioner>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func,
    _Partitioner&& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    _Index_type _Step,
    const _Function& _Func);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const static_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    const simple_partitioner& _Part);

template <typename _Index_type, typename _Function>
void parallel_for(
    _Index_type first,
    _Index_type last,
    const _Function& _Func,
    affinity_partitioner& _Part);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Index_type`  
 イテレーションの使用されているインデックスの型。  
  
 `_Function`  
 各イテレーションで実行される関数の型。  
  
 `_Partitioner`  
 指定された範囲のパーティション分割に使用されるパーティショナーの型。  
  
 `first`  
 イテレーションに含まれる最初のインデックス。  
  
 `last`  
 過去のイテレーションに含まれる最後のインデックスのいずれかのインデックス。  
  
 `_Step`  
 ステップから反復処理するときに使用する値`first`に`last`します。 ステップは、正の値である必要があります。 [invalid_argument](../../../standard-library/invalid-argument-class.md)ステップが 1 未満である場合にスローされます。  
  
 `_Func`  
 各イテレーションで実行される関数。 ラムダ式、関数ポインター、またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートする任意のオブジェクト`void operator()(_Index_type)`します。  
  
 `_Part`  
 パーティショナーのオブジェクトへの参照。 引数には、いずれかを指定できます`const` [auto_partitioner](auto-partitioner-class.md)`&`、 `const` [static_partitioner](static-partitioner-class.md)`&`、 `const` [simple_パーティショナー](simple-partitioner-class.md) `&`または[affinity_partitioner](affinity-partitioner-class.md) `&`場合、 [affinity_partitioner](affinity-partitioner-class.md)オブジェクトを使用して、参照は非定数の左辺値である必要がありますアルゴリズムが再利用する将来のループの状態を保存するために参照します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。[並列アルゴリズム](../../../parallel/concrt/parallel-algorithms.md)します。  
  
##  <a name="parallel_for_each"></a>  parallel_for_each  
 `parallel_for_each` は、指定された関数を範囲内の各要素に並列で適用します。 意味的には `for_each` 名前空間の `std` 関数と同等ですが、要素に対する反復処理が並列で行われる点、および反復処理の順序が指定されていない点が異なります。 引数 `_Func` は、`operator()(T)` の形式の関数呼び出し演算子をサポートしている必要があります (`T` パラメーターは反復処理するコンテナーの項目の種類を示します)。  
  
```
template <typename _Iterator, typename _Function>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func);

template <typename _Iterator, typename _Function, typename _Partitioner>
void parallel_for_each(
    _Iterator first,
    _Iterator last,
    const _Function& _Func,
    _Partitioner&& _Part);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 コンテナーを反復処理するために使用されている反復子の型。  
  
 `_Function`  
 範囲内の各要素に適用される関数の型。  
  
 `_Partitioner`  
 `first`  
 並列反復処理に含まれる最初の要素の位置を示す反復子。  
  
 `last`  
 並列反復処理に含まれる最後の要素の後ろのいずれかの位置を示す反復子。  
  
 `_Func`  
 範囲内の各要素に適用されるユーザー定義関数オブジェクト。  
  
 `_Part`  
 パーティショナーのオブジェクトへの参照。 引数には、いずれかを指定できます`const` [auto_partitioner](auto-partitioner-class.md)`&`、 `const` [static_partitioner](static-partitioner-class.md)`&`、 `const` [simple_パーティショナー](simple-partitioner-class.md) `&`または[affinity_partitioner](affinity-partitioner-class.md) `&`場合、 [affinity_partitioner](affinity-partitioner-class.md)オブジェクトを使用して、参照は非定数の左辺値である必要がありますアルゴリズムが再利用する将来のループの状態を保存するために参照します。  
  
### <a name="remarks"></a>Remarks  
 [auto_partitioner](auto-partitioner-class.md)明示的なパーティショナーをなしのオーバー ロードが適用されます。  
  
 ランダムをサポートしない反復子アクセスのみ[auto_partitioner](auto-partitioner-class.md)はサポートされています。  
  
 詳細については、次を参照してください。[並列アルゴリズム](../../../parallel/concrt/parallel-algorithms.md)します。  
  
##  <a name="parallel_invoke"></a>  parallel_invoke  
 パラメーターとして渡された関数オブジェクトを並列実行し、実行が完了するまでブロックします。 各関数オブジェクトは、ラムダ式、関数へのポインター、またはシグネチャ `void operator()()` を持つ関数呼び出し演算子をサポートするオブジェクトになります。  
  
```
template <typename _Function1, typename _Function2>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2);

template <typename _Function1, typename _Function2, typename _Function3>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9);

template <typename _Function1,
    typename _Function2,
    typename _Function3,
    typename _Function4,
    typename _Function5,
    typename _Function6,
    typename _Function7,
    typename _Function8,
    typename _Function9,
    typename _Function10>
void parallel_invoke(
    const _Function1& _Func1,
    const _Function2& _Func2,
    const _Function3& _Func3,
    const _Function4& _Func4,
    const _Function5& _Func5,
    const _Function6& _Func6,
    const _Function7& _Func7,
    const _Function8& _Func8,
    const _Function9& _Func9,
    const _Function10& _Func10);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function1`  
 並列で実行される最初の関数オブジェクトの型。  
  
 `_Function2`  
 並列で実行される 2 番目の関数オブジェクトの型。  
  
 `_Function3`  
 並列で実行する 3 番目の関数オブジェクトの型。  
  
 `_Function4`  
 並列で実行する 4 番目の関数オブジェクトの型。  
  
 `_Function5`  
 並列で実行する 5 番目の関数オブジェクトの型。  
  
 `_Function6`  
 並列で実行する 6 番目の関数オブジェクトの型。  
  
 `_Function7`  
 並列で実行される 7 番目の関数オブジェクトの型。  
  
 `_Function8`  
 並列で実行する 8 番目の関数オブジェクトの型。  
  
 `_Function9`  
 並列で実行される 9 番目の関数オブジェクトの型。  
  
 `_Function10`  
 並列で実行される 10 番目の関数オブジェクトの型。  
  
 `_Func1`  
 並列で実行される最初の関数オブジェクト。  
  
 `_Func2`  
 並列で実行される 2 つ目の関数オブジェクト。  
  
 `_Func3`  
 並列で実行される 3 つ目の関数オブジェクト。  
  
 `_Func4`  
 並列で実行する 4 番目の関数オブジェクト。  
  
 `_Func5`  
 並列で実行する 5 番目の関数オブジェクト。  
  
 `_Func6`  
 並列で実行する 6 番目の関数オブジェクト。  
  
 `_Func7`  
 並列で実行される 7 番目の関数オブジェクト。  
  
 `_Func8`  
 並列で実行する 8 番目の関数オブジェクト。  
  
 `_Func9`  
 並列で実行される 9 番目の関数オブジェクト。  
  
 `_Func10`  
 並列で実行される 10 番目の関数オブジェクト。  
  
### <a name="remarks"></a>Remarks  
 パラメーターは、呼び出し元のコンテキストのインラインを実行する可能性がありますとの 1 つまたは複数の関数オブジェクトを指定することに注意してください。  
  
 1 つまたは複数のパラメーターとしてこの関数に渡される関数オブジェクトは、例外をスローする場合、ランタイムは、選択した場合のような例外が 1 つを選択し、呼び出しから伝達されること`parallel_invoke`します。  
  
 詳細については、次を参照してください。[並列アルゴリズム](../../../parallel/concrt/parallel-algorithms.md)します。  
  
##  <a name="parallel_radixsort"></a>  parallel_radixsort  
 基数並べ替えアルゴリズムを使用して、指定された範囲の要素を降順以外の順序で配置します。 これは安定した並べ替え関数で、符号なし整数 (キーなど) に分類されるように要素を投影する投射関数を必要とします。 並べ替えられる要素には既定の初期化が必要です。  
  
```
template<typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Allocator, typename _Random_iterator>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator, typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator, typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);

template<typename _Allocator,
    typename _Random_iterator,
    typename _Function>
inline void parallel_radixsort(
    const _Allocator& _Alloc,
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Proj_func,
    const size_t _Chunk_size = 256* 256);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Random_iterator`  
 入力範囲の反復子の型。  
  
 `_Allocator`  
 C++ 標準ライブラリの互換性のあるメモリ アロケーターの型。  
  
 `_Function`  
 射影関数の型。  
  
 `_Begin`  
 並べ替えられる範囲内の最初の要素の位置を示すランダム アクセス反復子。  
  
 `_End`  
 並べ替えられる範囲内の最後の要素の 1 つ後ろの位置を示すランダム アクセス反復子。  
  
 `_Alloc`  
 C++ 標準ライブラリの互換性のあるメモリ アロケーターのインスタンス。  
  
 `_Proj_func`  
 要素を整数値に変換するユーザー定義射影関数オブジェクト。  
  
 `_Chunk_size`  
 並列実行用に 2 つに分割するチャンクの最小サイズ。  
  
### <a name="remarks"></a>Remarks  
 すべてのオーバー ロードを必要と`n * sizeof(T)`追加領域は、場所`n`が並べ替えられる要素の数と`T`要素の型は、します。 シグネチャを持つの単項プロジェクション ファンクター`I _Proj_func(T)`キー指定されると、要素を返すために必要な場所`T`要素の型と`I`は符号なし整数のような型。  
  
 射影関数を指定しない場合は、整数型の要素を単純に返す既定の射影関数が使用されます。 関数は、要素の射影関数がない場合は、整数型でない場合はコンパイルに失敗します。  
  
 アロケーターの型またはインスタンスでは、C++ 標準ライブラリのメモリ アロケーターを指定しない場合`std::allocator<T>`バッファーを割り当てるために使用します。  
  
 アルゴリズムは入力範囲を 2 つのチャンクに分割し、連続して各チャンクを並列で実行するための 2 つのサブ チャンクに分割します。 省略可能な引数`_Chunk_size`サイズのチャンクを処理する必要がある、アルゴリズムに示すために使用できます <`_Chunk_size`逐次的にします。  
  
##  <a name="parallel_reduce"></a>  parallel_reduce  
 連続する部分的な合計を計算することで、指定された範囲のすべての要素の合計を計算します。または、指定された二項演算を使用して取得した、合計以外の連続する部分的な結果を並列で計算します。 `parallel_reduce` は `std::accumulate` と意味が同じです。ただし、結合のための二項演算と、初期値ではなく ID 値が必要です。  
  
```
template<typename _Forward_iterator>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity);

template<typename _Forward_iterator, typename _Sym_reduce_fun>
inline typename std::iterator_traits<_Forward_iterator>::value_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const typename std::iterator_traits<_Forward_iterator>::value_type& _Identity,
    _Sym_reduce_fun _Sym_fun);

template<typename _Reduce_type,
    typename _Forward_iterator,
    typename _Range_reduce_fun,
    typename _Sym_reduce_fun>
inline _Reduce_type parallel_reduce(
    _Forward_iterator _Begin,
    _Forward_iterator _End,
    const _Reduce_type& _Identity,
    const _Range_reduce_fun& _Range_fun,
    const _Sym_reduce_fun& _Sym_fun);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Forward_iterator`  
 入力範囲の反復子の型。  
  
 `_Sym_reduce_fun`  
 対称リダクション関数の型。 関数の型シグネチャを持つ必要があります`_Reduce_type _Sym_fun(_Reduce_type, _Reduce_type)`_Reduce_type が同じ id の種類と削減の結果の型として、します。 3 番目のオーバー ロードでの出力の種類で一貫性のあるあります`_Range_reduce_fun`します。  
  
 `_Reduce_type`  
 入力を減らすには、入力要素の型が異なる可能性がある型。 戻り値と id 値は、この型があります。  
  
 `_Range_reduce_fun`  
 範囲のリダクション関数の型。 関数の型シグネチャを持つ必要があります`_Reduce_type _Range_fun(_Forward_iterator, _Forward_iterator, _Reduce_type)`_Reduce_type は同じ id の種類と削減の結果の型として。  
  
 `_Begin`  
 入力反復子の範囲の最初の要素をアドレス指定にすることです。  
  
 `_End`  
 縮小の範囲の最後の要素の次の位置を 1 つである要素を示す入力反復子。  
  
 `_Identity`  
 Id 値`_Identity`減少の結果の型と同じ型のほか、`value_type`番目と 2 番目のオーバー ロードの反復子の。 3 番目のオーバー ロードでは、id 値の削減、結果の型と同じ型がありますが異なる場合があります、`value_type`の反復子。 適切な値がありますように範囲の減少演算子`_Range_fun`型の 1 つの要素の範囲に適用すると、 `value_type` 、id の値が値型の値の型キャストのように動作し、 `value_type` id の種類にします。  
  
 `_Sym_fun`  
 2 番目の削減に使用される対称関数。 詳細については、「解説」を参照してください。  
  
 `_Range_fun`  
 削減の最初のフェーズで使用される関数。 詳細については、「解説」を参照してください。  
  
### <a name="return-value"></a>戻り値  
 減少の結果。  
  
### <a name="remarks"></a>Remarks  
 並列リダクションを実行するのには、関数は範囲を基になるスケジューラに使用できるワーカーの数に基づくチャンクに分割します。 2 つのフェーズで減らすことが、最初のフェーズは、各チャンク内での削減を実行しますおよび 2 番目のフェーズは、各チャンクから部分的な結果の間の削減を実行します。  
  
 最初のオーバー ロードである必要があります、反復子の`value_type`、 `T`id 値の種類と削減の結果型と同じであります。 要素型 T は、演算子を提供する必要があります`T T::operator + (T)`各チャンク内の要素を削減します。 同じ操作は、2 番目のフェーズもで使用されます。  
  
 2 番目のオーバー ロードも必要ですが、反復子の`value_type`id 値の種類と削減の結果型と同じであります。 指定された二項演算子`_Sym_fun`は最初のフェーズの初期値としての id 値で、両方の縮小フェーズで使用します。  
  
 3 番目のオーバー ロードでは、id 値の種類する必要がありますと同じである削減結果の型が、反復子の`value_type`両方に異なる可能性があります。 範囲のリダクション関数`_Range_fun`identity 値を持つ最初のフェーズでは、初期値では、および二項関数として使用`_Sym_reduce_fun`2 番目のフェーズで結果を sub に適用されます。  
  
##  <a name="parallel_sort"></a>  parallel_sort  
 指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って、並列に配置します。 この関数は、比較ベースで不安定なインプレース並べ替えという点で `std::sort` と意味が同じです。  
  
```
template<typename _Random_iterator>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End);

template<typename _Random_iterator,typename _Function>
inline void parallel_sort(
    const _Random_iterator& _Begin,
    const _Random_iterator& _End,
    const _Function& _Func,
    const size_t _Chunk_size = 2048);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Random_iterator`  
 入力範囲の反復子の型。  
  
 `_Function`  
 バイナリ比較ファンクターの型。  
  
 `_Begin`  
 並べ替えられる範囲内の最初の要素の位置を示すランダム アクセス反復子。  
  
 `_End`  
 並べ替えられる範囲内の最後の要素の 1 つ後ろの位置を示すランダム アクセス反復子。  
  
 `_Func`  
 順序の一連の要素によって満たされるように比較の基準を定義するユーザー定義の述語関数オブジェクト。 二項述語は 2 つの引数を受け取り、条件が満たされている場合は `true`、満たされていない場合は `false` を返します。 この比較子関数は、シーケンスからの要素のペアで厳密弱順序を強制する必要があります。  
  
 `_Chunk_size`  
 並列実行用に 2 つに分割するチャンクの最小サイズ。  
  
### <a name="remarks"></a>Remarks  
 最初のオーバー ロードはバイナリ比較演算子を使用して`std::less`します。  
  
 2 番目の使用をオーバー ロード シグネチャを持つ必要があります指定された二項比較演算子`bool _Func(T, T)`場所`T`入力範囲の要素の種類です。  
  
 アルゴリズムは入力範囲を 2 つのチャンクに分割し、連続して各チャンクを並列で実行するための 2 つのサブ チャンクに分割します。 省略可能な引数`_Chunk_size`サイズのチャンクを処理する必要がある、アルゴリズムに示すために使用できます <`_Chunk_size`逐次的にします。  
  
##  <a name="parallel_transform"></a>  parallel_transform  
 指定された関数オブジェクトをソース範囲内の各要素、または 2 つのソース範囲内の要素のペアに適用し、関数オブジェクトの戻り値をコピー先の範囲に並列でコピーします。 この関数は、意味的には `std::transform` と同じです。  
  
```
template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const auto_partitioner& _Part = auto_partitioner());

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const static_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    const simple_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Output_iterator,
    typename _Unary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Output_iterator _Result,
    const _Unary_operator& _Unary_op,
    affinity_partitioner& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator,
    typename _Partitioner>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
 first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op,
    _Partitioner&& _Part);

template <typename _Input_iterator1,
    typename _Input_iterator2,
    typename _Output_iterator,
    typename _Binary_operator>
_Output_iterator parallel_transform(
    _Input_iterator1 first1,
    _Input_iterator1 last1,
    _Input_iterator2
 first2,
    _Output_iterator _Result,
    const _Binary_operator& _Binary_op);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Input_iterator1`  
 最初のページとのみ入力反復子の型。  
  
 `_Output_iterator`  
 出力反復子の型。  
  
 `_Unary_operator`  
 入力範囲の各要素に対して実行される単項関数記号の型。  
  
 `_Input_iterator2`  
 2 番目の入力反復子の型。  
  
 `_Binary_operator`  
 2 つのソース範囲の要素上で実行ペアワイズ バイナリ ファンクターの型。  
  
 `_Partitioner`  
 `first1`  
 最初のページまたは操作するだけのソース範囲内の最初の要素の位置を示す入力反復子。  
  
 `last1`  
 1 つの後ろの位置の最後の要素、最初のページまたは操作するソース範囲のみを示す入力反復子。  
  
 `_Result`  
 ターゲット範囲の最初の要素の位置を示す出力反復子。  
  
 `_Unary_op`  
 ソース範囲内の各要素に適用されるユーザー定義の単項関数オブジェクト。  
  
 `_Part`  
 パーティショナーのオブジェクトへの参照。 引数には、いずれかを指定できます`const` [auto_partitioner](auto-partitioner-class.md)`&`、 `const` [static_partitioner](static-partitioner-class.md)`&`、 `const` [simple_パーティショナー](simple-partitioner-class.md) `&`または[affinity_partitioner](affinity-partitioner-class.md) `&`場合、 [affinity_partitioner](affinity-partitioner-class.md)オブジェクトを使用して、参照は非定数の左辺値である必要がありますアルゴリズムが再利用する将来のループの状態を保存するために参照します。  
  
 `first2`  
 操作する 2 番目のソース範囲内の最初の要素の位置を示す入力反復子。  
  
 `_Binary_op`  
 ペアワイズ、2 つのソース範囲を順方向順序で適用されるユーザー定義の二項関数オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 関数オブジェクトで変換された出力要素を受け取るターゲット範囲の最後の要素の 1 つ後ろの位置を示す出力反復子。  
  
### <a name="remarks"></a>Remarks  
 [auto_partitioner](auto-partitioner-class.md)明示的なパーティショナーを引数なしのオーバー ロードが適用されます。  
  
 ランダムをサポートしない反復子アクセスのみ[auto_partitioner](auto-partitioner-class.md)はサポートされています。  
  
 引数を受け取るオーバー ロード`_Unary_op`単項ファンクタを入力の範囲内の各要素に適用することにより出力範囲入力範囲に変換します。 `_Unary_op` シグネチャを持つ関数呼び出し演算子をサポートする必要があります`operator()(T)`場所`T`が反復処理中の範囲の値の型。  
  
 引数を受け取るオーバー ロード`_Binary_op`最初の入力の範囲と 2 番目の入力の範囲から 1 つの要素から 1 つの要素のバイナリ ファンクタを適用することで、2 つの入力範囲を出力範囲に変換します。 `_Binary_op` シグネチャを持つ関数呼び出し演算子をサポートする必要があります`operator()(T, U)`場所`T`、`U`は 2 つの入力反復子の値の型。  
  
 詳細については、次を参照してください。[並列アルゴリズム](../../../parallel/concrt/parallel-algorithms.md)します。  
  
##  <a name="receive"></a>  receive  
 receive の一般的な実装です。これにより、コンテキストで 1 つのソースからのデータを待機し、受け取った値をフィルター処理できます。  
  
```
template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    _Inout_ ISource<T>* _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);

template <class T>
T receive(
    ISource<T>& _Src,
    typename ITarget<T>::filter_method const& _Filter_proc,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 ペイロードの型。  
  
 `_Src`  
 ポインターまたはデータが必要です元のソースへの参照。  
  
 `_Timeout`  
 データ (ミリ秒単位) では、メソッドが対象の最大時間。  
  
 `_Filter_proc`  
 メッセージを受け入れられる必要があるかどうかを決定するフィルター関数。  
  
### <a name="return-value"></a>戻り値  
 ペイロードの種類のソースからの値。  
  
### <a name="remarks"></a>Remarks  
 場合、パラメーター`_Timeout`定数以外の値を持つ`COOPERATIVE_TIMEOUT_INFINITE`、例外[operation_timed_out](operation-timed-out-class.md)が、一定の時間には、メッセージを受信する前に有効期限が切れる場合にスローされます。 使用する必要があります長さ 0 のタイムアウトを設定する場合、 [try_receive](concurrency-namespace-functions.md)関数を呼び出すのではなく`receive`のタイムアウトで`0`(ゼロ) より効率的でありのタイムアウト例外をスローしません。  
  
 詳細については、次を参照してください。[メッセージを渡す関数](../../../parallel/concrt/message-passing-functions.md)します。  
  
##  <a name="run_with_cancellation_token"></a>  run_with_cancellation_token  
 関数オブジェクトを、指定されたキャンセル トークンのコンテキストですばやく同期的に実行します。  
  
```
template<typename _Function>
void run_with_cancellation_token(
    const _Function& _Func,
    cancellation_token _Ct);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 呼び出される関数オブジェクトの型。  
  
 `_Func`  
 実行される関数オブジェクト。 このオブジェクトは、void(void) のシグネチャを持つ関数呼び出し演算子をサポートする必要があります。  
  
 `_Ct`  
 関数オブジェクトの暗黙的なキャンセルを制御するキャンセル トークン。 使用`cancellation_token::none()`存在する可能性がキャンセルされる親タスク グループからの暗黙的なキャンセルの関数を実行する場合。  
  
### <a name="remarks"></a>Remarks  
 関数オブジェクトでは、任意の割り込みポイントがあるときにトリガーされる、`cancellation_token`が取り消されました。 明示的なトークン`_Ct`この分離は`_Func`から親キャンセルの場合は、親がある別のトークンまたはトークンがありません。  
  
##  <a name="send"></a>  send  
 ターゲットがメッセージを受け入れるか拒否するまで待機する同期送信操作です。  
  
```
template <class T>
bool send(_Inout_ ITarget<T>* _Trg, const T& _Data);

template <class T>
bool send(ITarget<T>& _Trg, const T& _Data);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 ペイロードの型。  
  
 `_Trg`  
 ポインターまたはデータが送信されるターゲットへの参照。  
  
 `_Data`  
 送信されるデータへの参照。  
  
### <a name="return-value"></a>戻り値  
 `true` メッセージが受け入れられた場合`false`それ以外の場合。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。[メッセージを渡す関数](../../../parallel/concrt/message-passing-functions.md)します。  
  
##  <a name="set_ambient_scheduler"></a>  set_ambient_scheduler  
  
```
inline void set_ambient_scheduler(std::shared_ptr<::Concurrency::scheduler_interface> _Scheduler);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Scheduler`  
  
##  <a name="set_task_execution_resources"></a>  set_task_execution_resources  
 同時実行ランタイムの内部ワーカー スレッドが使用する実行リソースを、指定された関係セットに制限します。  
  
 このメソッドの呼び出しは、リソース マネージャーの作成前、または 2 つのリソース マネージャーの有効期間の間のみ有効です。 これは、呼び出し時にリソース マネージャーが存在しない限り複数回呼び出すことができます。 関係の制限が設定されたら、次の有効な `set_task_execution_resources` メソッド呼び出しまで保持されます。  
  
 指定された関係マスクは、プロセス関係マスクのサブセットである必要はありません。 プロセス関係は必要に応じて更新されます。  
  
```
void __cdecl set_task_execution_resources(
    DWORD_PTR _ProcessAffinityMask);

void __cdecl set_task_execution_resources(
    unsigned short count,
    PGROUP_AFFINITY _PGroupAffinity);
```  
  
### <a name="parameters"></a>パラメーター  
 `_ProcessAffinityMask`  
 同時実行ランタイムのワーカー スレッドに制限する場合は、関係マスク。 現在のプロセッサ グループのサブセットに同時実行ランタイムを制限する場合にのみ、64 のハードウェア スレッドよりも大きい値を持つシステムでこのメソッドを使用します。 一般に、コンピューターのアフィニティを 64 ハードウェア スレッドよりも大きい値を制限する、パラメーターとしてグループとのアフィニティの配列を受け取るメソッドのバージョンを使用する必要があります。  
  
 `count`  
 数`GROUP_AFFINITY`パラメーターで指定された配列内のエントリ`_PGroupAffinity`します。  
  
 `_PGroupAffinity`  
 配列の`GROUP_AFFINITY`エントリ。  
  
### <a name="remarks"></a>Remarks  
 メソッドがスローされます、 [invalid_operation](invalid-operation-class.md)リソース マネージャーは、メソッドが呼び出された時点で存在する場合は例外と[invalid_argument](../../../standard-library/invalid-argument-class.md)アフィニティでは、空のセットで結果が指定された場合は例外リソース。  
  
 Windows 7 のバージョンのオペレーティング システムで使用またはそれ以降、グループとのアフィニティの配列をパラメーターとして受け取るメソッドのバージョンがあるのみ必要があります。 それ以外の場合、 [invalid_operation](invalid-operation-class.md)例外がスローされます。  
  
 このメソッドが呼び出された後、プロセスの関係をプログラムで変更に限定されますアフィニティを再評価する Resource Manager は発生しません。 したがって、アフィニティを処理するすべての変更は、このメソッドを呼び出す前に作成する必要があります。  
  
##  <a name="swap"></a>  swap  
 2 つの `concurrent_vector` オブジェクトの要素を交換します。  
  
```
template<typename T, class _Ax>
inline void swap(
    concurrent_vector<T, _Ax>& _A,
    concurrent_vector<T, _Ax>& _B);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 同時実行ベクターに格納されている要素のデータ型。  
  
 `_Ax`  
 同時実行ベクターのアロケーターの型。  
  
 `_A`  
 要素が、同時実行ベクターと交換される、同時実行ベクター`_B`します。  
  
 `_B`  
 交換する要素を提供する同時実行ベクターまたは要素の同時実行ベクターと交換するベクター`_A`します。  
  
### <a name="remarks"></a>Remarks  
 テンプレート関数は、コンテナー クラスに特化したアルゴリズム`concurrent_vector`メンバー関数の実行に`_A`します。 [concurrent_vector::swap](concurrent-vector-class.md#swap)( `_B`)。 これらは、コンパイラによる関数テンプレートの部分的な順序付けのインスタンスです。 テンプレートと関数呼び出しの照合が一意にならないようにテンプレート関数がオーバーロードされた場合、コンパイラは、最も特化したバージョンのテンプレート関数を選択します。 テンプレート関数の一般的なバージョン`template <class T> void swap(T&, T&)`アルゴリズムでクラスは代入によって機能し、低速な操作です。 各コンテナー内の特化バージョンのほうが、コンテナー クラスの内部表現で使用できるため大幅に高速になります。  
  
 このメソッドは同時実行セーフではありません。 他のスレッドも操作を行って同時実行ベクターのどちらかでこのメソッドを呼び出すときにすることを確認する必要があります。  
  
##  <a name="task_from_exception"></a>  task_from_exception  
  
```
template<typename _TaskType, typename _ExType>
task<_TaskType> task_from_exception(
    _ExType _Exception,
    const task_options& _TaskOptions = task_options());
```  
  
### <a name="parameters"></a>パラメーター  
 `_TaskType`  
 `_ExType`  
 `_Exception`  
 `_TaskOptions`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="task_from_result"></a>  task_from_result  
  
```
template<typename T>
task<T> task_from_result(
    T _Param,
    const task_options& _TaskOptions = task_options());

inline task<bool> task_from_result(ool _Param);

inline task<void> task_from_result(
    const task_options& _TaskOptions = task_options());
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 `_Param`  
 `_TaskOptions`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="trace_agents_register_name"></a>  Trace_agents_register_name  
 指定された名前を、ETW トレースのメッセージ ブロックまたはエージェントに関連付けます。  
  
```
template <class T>
void Trace_agents_register_name(
    _Inout_ T* _PObject,
    _In_z_ const wchar_t* _Name);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 オブジェクトの型。 これは通常、メッセージ ブロックまたはエージェントです。  
  
 `_PObject`  
 メッセージ ブロックまたはトレースに名前が、エージェントへのポインター。  
  
 `_Name`  
 指定したオブジェクトの名前。  
  
##  <a name="try_receive"></a>  try_receive  
 try-receive の一般的な実装です。これにより、コンテキストで 1 つのソースに対してのみデータの検索を実行し、受け取った値をフィルター処理できます。 データが準備されていない場合、メソッドは false を返します。  
  
``` 
template <class T>
bool try_receive(_Inout_ ISource<T>* _Src, T& _value);

template <class T>
bool try_receive(
    _Inout_ ISource<T>* _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);

template <class T>
bool try_receive(ISource<T>& _Src, T& _value);

template <class T>
bool try_receive(
    ISource<T>& _Src,
    T& _value,
    typename ITarget<T>::filter_method const& _Filter_proc);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 ペイロードの種類  
  
 `_Src`  
 ポインターまたはデータが必要です元のソースへの参照。  
  
 `_value`  
 結果が配置される場所への参照。  
  
 `_Filter_proc`  
 メッセージを受け入れられる必要があるかどうかを決定するフィルター関数。  
  
### <a name="return-value"></a>戻り値  
 A`bool`にペイロードが格納されたかどうかを示すを値`_value`します。  
  
### <a name="remarks"></a>Remarks  
 詳細については、次を参照してください。[メッセージを渡す関数](../../../parallel/concrt/message-passing-functions.md)します。  
  
##  <a name="wait"></a>  wait  
 指定した時間だけ現在のコンテキストを停止します。  
  
```
void __cdecl wait(unsigned int _Milliseconds);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Milliseconds`  
 現在のコンテキストを停止するミリ秒数。 場合、`_Milliseconds`パラメーター値に設定されて`0`、現在のコンテキストが実行を続行する前に実行可能なその他のコンテキストを生成する必要があります。  
  
### <a name="remarks"></a>Remarks  
 このメソッドは同時実行ランタイム スケジューラのコンテキストで呼び出されると、スケジューラは、基になるリソースで実行する別のコンテキストを紹介します。 スケジューラは本質的に協調的であるために、このコンテキストは、指定されたミリ秒数後に正確に再開できません。 スケジューラが、スケジューラに協調的を生成しないその他のタスクの実行でビジー状態の場合は、待機時間が確実なない可能性があります。  
  
##  <a name="when_all"></a>  when_all  
 引数として指定されたすべてのタスクが正常に完了したときに正常に完了するタスクを作成します。  
  
```
template <typename _Iterator>
auto when_all(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options()) -> 
    decltype (details::_WhenAllImpl<typename std::iterator_traits<_Iterator>::value_type::result_type,
    _Iterator>::_Perform(_TaskOptions, _Begin,  _End));
```   
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 入力反復子の型。  
  
 `_Begin`  
 結果のタスクに組み込まれる要素範囲内にある最初の要素の位置。  
  
 `_End`  
 結果のタスクに組み込まれる要素範囲外にある最初の要素の位置。  
  
 `_TaskOptions`  
  
### <a name="return-value"></a>戻り値  
 入力したすべてのタスクが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::vector<T>>` になります。 入力したタスクの種類が `void` である場合、出力のタスクも `task<void>` になります。  
  
### <a name="remarks"></a>Remarks  
 `when_all` は、その結果、`task` を生成する、非ブロッキング関数です。 異なり[task::wait](task-class.md#wait)ASTA (アプリケーション STA) スレッドでの UWP アプリでこの関数を呼び出しても安全になります。  
  
 取り消されたタスクのいずれか、または例外をスローは早い段階で取り消された状態で、返されたタスクは完了し、例外が発生しました、1 つは場合がスローされますを呼び出す場合、 [task::get](task-class.md#get)または`task::wait`タスクにします。  
  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。  
  
##  <a name="when_any"></a>  when_any  
 引数として指定されたいずれかのタスクが正常に完了したときに正常に完了するタスクを作成します。  
  
```
template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    const task_options& _TaskOptions = task_options()) 
    -> decltype (
        details::_WhenAnyImpl<
            typename std::iterator_traits<_Iterator>::value_type::result_type,
            _Iterator>::_Perform(_TaskOptions, _Begin, _End));

template<typename _Iterator>
auto when_any(
    _Iterator _Begin,
    _Iterator _End,
    cancellation_token _CancellationToken) 
       -> decltype (
           details::_WhenAnyImpl<
               typename std::iterator_traits<_Iterator>::value_type::result_type,
               _Iterator>::_Perform(_CancellationToken._GetImplValue(), _Begin, _End));
```   
  
### <a name="parameters"></a>パラメーター  
 `_Iterator`  
 入力反復子の型。  
  
 `_Begin`  
 結果のタスクに組み込まれる要素範囲内にある最初の要素の位置。  
  
 `_End`  
 結果のタスクに組み込まれる要素範囲外にある最初の要素の位置。  
  
 `_TaskOptions`  
 `_CancellationToken`  
 返されたタスクの取り消しを制御するキャンセル トークン。 キャンセル トークンを指定しない場合、結果のタスクは、完了の原因となったタスクのキャンセル トークンを受け取ります。  
  
### <a name="return-value"></a>戻り値  
 入力したタスクのいずれかが正常に完了したときに正常に完了するタスク。 入力したタスクの種類が `T` である場合、この関数の出力は `task<std::pair<T, size_t>>>` になります。ここでは、pair の最初の要素は完了したタスクの結果であり、2 番目の要素は完了したタスクのインデックスです。 入力したタスクの種類が `void` である場合、出力は `task<size_t>` になります。この場合、結果は完了したタスクのインデックスです。  
  
### <a name="remarks"></a>Remarks  
 `when_any` は、その結果、`task` を生成する、非ブロッキング関数です。 異なり[task::wait](task-class.md#wait)ASTA (アプリケーション STA) スレッドでの UWP アプリでこの関数を呼び出しても安全になります。  
  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
