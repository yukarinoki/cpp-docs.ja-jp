---
title: CurrentScheduler クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- CurrentScheduler
- CONCRT/concurrency::CurrentScheduler
- CONCRT/concurrency::CurrentScheduler::Create
- CONCRT/concurrency::CurrentScheduler::CreateScheduleGroup
- CONCRT/concurrency::CurrentScheduler::Detach
- CONCRT/concurrency::CurrentScheduler::Get
- CONCRT/concurrency::CurrentScheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::CurrentScheduler::GetPolicy
- CONCRT/concurrency::CurrentScheduler::Id
- CONCRT/concurrency::CurrentScheduler::IsAvailableLocation
- CONCRT/concurrency::CurrentScheduler::RegisterShutdownEvent
- CONCRT/concurrency::CurrentScheduler::ScheduleTask
dev_langs:
- C++
helpviewer_keywords:
- CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 71ca69f645e548b1913904f692eb1c5fae167a9a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="currentscheduler-class"></a>CurrentScheduler クラス
呼び出し元コンテキストに関連付けられている現在のスケジューラの抽象化を表します。  
  
## <a name="syntax"></a>構文  
  
```
class CurrentScheduler;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[作成します。](#create)|動作が説明されている、新しいスケジューラを作成、`_Policy`パラメーターを呼び出し元のコンテキストにアタッチします。 新しく作成されたスケジューラは、呼び出し元のコンテキストの現在のスケジューラになります。|  
|[CreateScheduleGroup](#createschedulegroup)|オーバーロードされます。 呼び出し元のコンテキストに関連付けられているスケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョンで`_Placement`により、そのパラメーターで指定された場所で実行する方向に偏ってするを新しく作成されたスケジュール グループ内のタスクです。|  
|[デタッチ](#detach)|呼び出し元のコンテキストから現在のスケジューラをデタッチし、いずれかが存在する場合は、現在のスケジューラとして以前接続されているスケジューラを復元します。 呼び出し元のコンテキストがいずれかを使用して、コンテキストにアタッチされている以前のスケジューラで管理し、このメソッドから制御が戻た後、`CurrentScheduler::Create`または`Scheduler::Attach`メソッドです。|  
|[Get](#get)|現在のスケジューラとも呼ばれます、呼び出し元のコンテキストに関連付けられているスケジューラへのポインターを返します。|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|呼び出し元のコンテキストに関連付けられているスケジューラの仮想プロセッサの現在の数を返します。|  
|[GetPolicy](#getpolicy)|現在のスケジューラを使用して作成されたポリシーのコピーを返します。|  
|[Id](#id)|現在のスケジューラの一意の識別子を返します。|  
|[IsAvailableLocation](#isavailablelocation)|指定された場所が現在のスケジューラで使用できるかどうかを判断します。|  
|[RegisterShutdownEvent](#registershutdownevent)|Windows イベント ハンドルが渡された原因、`_ShutdownEvent`シグナル状態になる、現在のコンテキストに関連付けられているスケジューラがシャット ダウンし、それ自体を破棄するときのパラメーターです。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドでは、複数のシャット ダウン イベントを登録できます。|  
|[ScheduleTask](#scheduletask)|オーバーロードされます。 呼び出し元のコンテキストに関連付けられているスケジューラ内の軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョンで`_Placement`するが優先される指定した場所に実行するためにタスクをさせます。|  
  
## <a name="remarks"></a>コメント  
 スケジューラが存在しない場合 (を参照してください[スケジューラ](scheduler-class.md)) 呼び出し元のコンテキスト内で多くのメソッドに関連付けられている、`CurrentScheduler`クラスは、プロセスの既定のスケジューラの添付ファイルになります。 このような呼び出し中に、プロセスの既定のスケジューラが作成されたことがも予想します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CurrentScheduler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="create"></a> 作成します。 

 動作が説明されている、新しいスケジューラを作成、`_Policy`パラメーターを呼び出し元のコンテキストにアタッチします。 新しく作成されたスケジューラは、呼び出し元のコンテキストの現在のスケジューラになります。  
  
```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Policy`  
 新しく作成されたスケジューラの動作を説明するスケジューラ ポリシー。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラの添付ファイルは、スケジューラで暗黙的に参照カウントを配置します。  
  
 スケジューラの作成後、`Create`メソッドを呼び出す必要があります、 [currentscheduler::detach](#detach)スケジューラをシャット ダウンを許可するために、今後のいつかメソッドです。  
  
 このメソッドは既に別のスケジューラにアタッチされているコンテキストから呼び出されると、既存のスケジューラが、以前のスケジューラとして記憶し、新しく作成されたスケジューラは、現在のスケジューラになります。 呼び出すと、`CurrentScheduler::Detach`後で、前のスケジューラのメソッドは、現在のスケジューラとして復元されます。  
  
 このメソッドを含む、例外のさまざまな[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)と[invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)です。  
  
##  <a name="createschedulegroup"></a> CreateScheduleGroup 

 呼び出し元のコンテキストに関連付けられているスケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョンで`_Placement`により、そのパラメーターで指定された場所で実行する方向に偏ってするを新しく作成されたスケジュール グループ内のタスクです。  
  
```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Placement`  
 実行する方向には、スケジュール グループ内のタスクをバイアスは場所への参照。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたスケジュール グループへのポインター。 これは、`ScheduleGroup`オブジェクトには、初期の参照カウントを配置します。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
 呼び出す必要があります、[リリース](schedulegroup-class.md#release)作業のスケジュールを実行するときに、スケジュール グループのメソッドです。 スケジュールをスケジューラが破棄されますが、すべての作業キューに登録されている場合は、グループの完了します。  
  
 このスケジューラを明示的に作成した場合は、そこから現在のコンテキストをデタッチすることにより、スケジューラの参照を解放する前に、内のグループのスケジュールへのすべての参照を解放する必要がありますに注意してください。  
  
##  <a name="detach"></a> デタッチ 

 呼び出し元のコンテキストから現在のスケジューラをデタッチし、いずれかが存在する場合は、現在のスケジューラとして以前接続されているスケジューラを復元します。 呼び出し元のコンテキストがいずれかを使用して、コンテキストにアタッチされている以前のスケジューラで管理し、このメソッドから制御が戻た後、`CurrentScheduler::Create`または`Scheduler::Attach`メソッドです。  
  
```
static void __cdecl Detach();
```  
  
### <a name="remarks"></a>コメント  
 `Detach`メソッドが、スケジューラからの参照カウントを暗黙的に削除します。  
  
 呼び出し元のコンテキストにアタッチされているスケジューラがない場合は、このメソッドを呼び出すが、 [scheduler_not_attached](scheduler-not-attached-class.md)例外がスローされます。  
  
 コンテキストからこのメソッドを呼び出すには内部管理スケジューラ、またはメソッドを使用せずに添付されたコンテキストで、 [scheduler::attach](scheduler-class.md#attach)または[currentscheduler::create](#create)メソッドなります、 [improper_scheduler_detach](improper-scheduler-detach-class.md)例外がスローされます。  
  
##  <a name="get"></a> 取得 

 現在のスケジューラとも呼ばれます、呼び出し元のコンテキストに関連付けられているスケジューラへのポインターを返します。  
  
```
static Scheduler* __cdecl Get();
```  
  
### <a name="return-value"></a>戻り値  
 呼び出し元のコンテキスト (現在のスケジューラ) に関連付けられているスケジューラへのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。 その他の参照が配置されていない、`Scheduler`このメソッドによって返されるオブジェクト。  
  
##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors 

 呼び出し元のコンテキストに関連付けられているスケジューラの仮想プロセッサの現在の数を返します。  
  
```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラが呼び出し元のコンテキストでは、そのスケジューラの仮想プロセッサの現在の数に関連付けられている場合それ以外の場合、値`-1`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、呼び出し元のコンテキストが既にスケジューラに関連付けられていない場合スケジューラの添付ファイルには発生しません。  
  
 このメソッドからの戻り値は、呼び出し元のコンテキストに関連付けられているスケジューラの仮想プロセッサの数の瞬間的にサンプリングします。 この値は、返される、現在古いできます。  
  
##  <a name="getpolicy"></a> GetPolicy 

 現在のスケジューラを使用して作成されたポリシーのコピーを返します。  
  
```
static SchedulerPolicy __cdecl GetPolicy();
```  
  
### <a name="return-value"></a>戻り値  
 ポリシーのコピーを現在のスケジューラを使用して作成されました。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
##  <a name="id"></a> id 

 現在のスケジューラの一意の識別子を返します。  
  
```
static unsigned int __cdecl Id();
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラが呼び出し元のコンテキストでは、そのスケジューラの一意の識別子と関連付けられている場合それ以外の場合、値`-1`です。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、呼び出し元のコンテキストが既にスケジューラに関連付けられていない場合スケジューラの添付ファイルには発生しません。  
  
##  <a name="isavailablelocation"></a> IsAvailableLocation 

 指定された場所が現在のスケジューラで使用できるかどうかを判断します。  
  
```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Placement`  
 に関する現在のスケジューラをクエリする場所への参照。  
  
### <a name="return-value"></a>戻り値  
 場所がで指定するかどうかを示す、`_Placement`引数は、現在のスケジューラを使用できます。  
  
### <a name="remarks"></a>コメント  
 このメソッドは、呼び出し元のコンテキストが既にスケジューラに関連付けられていない場合スケジューラの添付ファイルには発生しません。  
  
 戻り値が指定された場所が使用できるかどうかの瞬間的にサンプリングに注意してください。 複数のスケジューラが存在する場合は、動的なリソース管理は追加または任意の時点でスケジューラからリソースを取り去ることがことができます。 この場合は、指定された場所は、可用性に変更できます。  
  
##  <a name="registershutdownevent"></a> RegisterShutdownEvent 

 Windows イベント ハンドルが渡された原因、`_ShutdownEvent`シグナル状態になる、現在のコンテキストに関連付けられているスケジューラがシャット ダウンし、それ自体を破棄するときのパラメーターです。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドでは、複数のシャット ダウン イベントを登録できます。  
  
```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```  
  
### <a name="parameters"></a>パラメーター  
 `_ShutdownEvent`  
 現在のコンテキストに関連付けられているスケジューラがシャット ダウンし、それ自体を破棄するときに、ランタイムによって通知される Windows イベント オブジェクトへのハンドル。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにアタッチされているスケジューラがない場合は、このメソッドを呼び出すが、 [scheduler_not_attached](scheduler-not-attached-class.md)例外がスローされます。  
  
##  <a name="scheduletask"></a> ScheduleTask 

 呼び出し元のコンテキストに関連付けられているスケジューラ内の軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョンで`_Placement`するが優先される指定した場所に実行するためにタスクをさせます。  
  
```
static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data);

static void __cdecl ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Proc`  
 軽量タスクの本体を実行するために実行する関数へのポインター。  
  
 `_Data`  
 タスクの本体にパラメーターとして渡されるデータへの void ポインターです。  
  
 `_Placement`  
 実行する方向には、軽量タスクをバイアスは場所への参照。  
  
### <a name="remarks"></a>コメント  
 呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [Scheduler クラス](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



