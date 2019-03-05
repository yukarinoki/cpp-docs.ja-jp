---
title: CurrentScheduler クラス
ms.date: 11/04/2016
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
helpviewer_keywords:
- CurrentScheduler class
ms.assetid: 31c20e0e-4cdf-49b4-8220-d726130aad2b
ms.openlocfilehash: a27ec7c25962b6addd26e61af8f33130d4c653ba
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326791"
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
|[作成します。](#create)|動作が説明されている新しいスケジューラを作成、`_Policy`パラメーター呼び出し元のコンテキストにアタッチします。 新しく作成されたスケジューラには、呼び出し元のコンテキストの現在のスケジューラになります。|
|[CreateScheduleGroup](#createschedulegroup)|オーバーロードされます。 呼び出し元のコンテキストに関連付けられたスケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョン`_Placement`にそのパラメーターで指定された場所で実行に偏っていますが、新しく作成したスケジュール グループ内のタスクが原因です。|
|[Detach](#detach)|呼び出し元のコンテキストから現在のスケジューラをデタッチし、存在する場合、現在のスケジューラとして以前に接続されているスケジューラを復元します。 呼び出し元のコンテキストがいずれかを使用して、コンテキストに接続されていたスケジューラによって管理し、このメソッドから制御が戻た後、`CurrentScheduler::Create`または`Scheduler::Attach`メソッド。|
|[Get](#get)|現在のスケジューラとも呼ばれます、呼び出し元コンテキストに関連付けられたスケジューラへのポインターを返します。|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|呼び出し元のコンテキストに関連付けられているスケジューラの仮想プロセッサの現在の数を返します。|
|[GetPolicy](#getpolicy)|現在のスケジューラが作成されたポリシーのコピーを返します。|
|[ID](#id)|現在のスケジューラの一意識別子を返します。|
|[IsAvailableLocation](#isavailablelocation)|特定の場所は、現在のスケジューラに収録されているかどうかを判断します。|
|[RegisterShutdownEvent](#registershutdownevent)|Windows のイベント ハンドルが渡された原因、`_ShutdownEvent`パラメーターがシグナル状態に、現在のコンテキストに関連付けられているスケジューラがシャット ダウンし、それ自体を破棄します。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドは、複数のシャット ダウン イベントを登録できます。|
|[ScheduleTask](#scheduletask)|オーバーロードされます。 呼び出し元のコンテキストに関連付けられたスケジューラ内での軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョン`_Placement`タスクが実行指定した位置に重きをさせます。|

## <a name="remarks"></a>Remarks

スケジューラがない場合 (を参照してください[スケジューラ](scheduler-class.md)) 呼び出し元のコンテキスト内で多くのメソッドに関連付けられた、`CurrentScheduler`クラスは、プロセスの既定のスケジューラの添付ファイルになります。 このような呼び出し中に、プロセスの既定のスケジューラが作成されたことがも予想します。

## <a name="inheritance-hierarchy"></a>継承階層

`CurrentScheduler`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="create"></a> 作成します。

動作が説明されている新しいスケジューラを作成、`_Policy`パラメーター呼び出し元のコンテキストにアタッチします。 新しく作成されたスケジューラには、呼び出し元のコンテキストの現在のスケジューラになります。

```
static void __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>パラメーター

*_Policy*<br/>
スケジューラ ポリシーを新しく作成されたスケジューラの動作について説明します。

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにスケジューラの添付ファイルは、スケジューラで暗黙的に参照カウントを配置します。

スケジューラの作成後、`Create`メソッドを呼び出す必要があります、 [currentscheduler::detach](#detach)スケジューラをシャット ダウンを許可するには、今後ある時点でのメソッド。

このメソッドは既に別のスケジューラにアタッチされているコンテキストから呼び出されると、既存のスケジューラは、以前のスケジューラとして記憶し、新しく作成されたスケジューラが現在のスケジューラになります。 呼び出すと、`CurrentScheduler::Detach`メソッドは、後で、前のスケジューラは、現在のスケジューラとして復元されます。

このメソッドが、さまざまな例外をスロー [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)と[invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)します。

##  <a name="createschedulegroup"></a> CreateScheduleGroup

呼び出し元のコンテキストに関連付けられたスケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョン`_Placement`にそのパラメーターで指定された場所で実行に偏っていますが、新しく作成したスケジュール グループ内のタスクが原因です。

```
static ScheduleGroup* __cdecl CreateScheduleGroup();

static ScheduleGroup* __cdecl CreateScheduleGroup(location& _Placement);
```

### <a name="parameters"></a>パラメーター

*(_P)*<br/>
実行中に、スケジュール グループ内のタスクをバイアスは場所への参照。

### <a name="return-value"></a>戻り値

新しく作成したスケジュール グループへのポインター。 これは、`ScheduleGroup`オブジェクトが配置される最初の参照数。

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。

呼び出す必要があります、[リリース](schedulegroup-class.md#release)作業のスケジュールを実行するときに、スケジュール グループのメソッド。 スケジューラでスケジュールを破棄グループにすべての作業がキューに置かれたときに完了します。

このスケジューラを明示的に作成した場合は、現在のコンテキストからデタッチすることにより、スケジューラ上への参照を解放する前に、内のグループをスケジュールするすべての参照を解放する必要がありますに注意してください。

##  <a name="detach"></a> デタッチ

呼び出し元のコンテキストから現在のスケジューラをデタッチし、存在する場合、現在のスケジューラとして以前に接続されているスケジューラを復元します。 呼び出し元のコンテキストがいずれかを使用して、コンテキストに接続されていたスケジューラによって管理し、このメソッドから制御が戻た後、`CurrentScheduler::Create`または`Scheduler::Attach`メソッド。

```
static void __cdecl Detach();
```

### <a name="remarks"></a>Remarks

`Detach`メソッドが、スケジューラから暗黙的に参照カウントを削除します。

呼び出し元のコンテキストにアタッチされているスケジューラがない場合は、このメソッドを呼び出すことになります、 [scheduler_not_attached](scheduler-not-attached-class.md)例外がスローされます。

内部と、スケジューラまたは以外のメソッドを使用して接続されていたコンテキストによって管理されているが、コンテキストからこのメソッドを呼び出す、 [scheduler::attach](scheduler-class.md#attach)または[currentscheduler::create](#create)メソッド発生する[improper_scheduler_detach](improper-scheduler-detach-class.md)例外がスローされます。

##  <a name="get"></a> 取得

現在のスケジューラとも呼ばれます、呼び出し元コンテキストに関連付けられたスケジューラへのポインターを返します。

```
static Scheduler* __cdecl Get();
```

### <a name="return-value"></a>戻り値

(現在のスケジューラ) の呼び出し元のコンテキストに関連付けられているスケジューラへのポインター。

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。 追加の参照は適用されません、`Scheduler`このメソッドによって返されるオブジェクト。

##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors

呼び出し元のコンテキストに関連付けられているスケジューラの仮想プロセッサの現在の数を返します。

```
static unsigned int __cdecl GetNumberOfVirtualProcessors();
```

### <a name="return-value"></a>戻り値

スケジューラが呼び出し元のコンテキストでは、そのスケジューラの仮想プロセッサの現在の数に関連付けられている場合それ以外の場合、値`-1`します。

### <a name="remarks"></a>Remarks

このメソッドは、呼び出し元のコンテキストが、スケジューラに関連付けられていない場合はスケジューラの添付ファイルには発生しません。

このメソッドからの戻り値は、呼び出し元のコンテキストに関連付けられているスケジューラの仮想プロセッサの数の瞬間的にサンプリングします。 この値は古いが返される時点です。

##  <a name="getpolicy"></a> GetPolicy

現在のスケジューラが作成されたポリシーのコピーを返します。

```
static SchedulerPolicy __cdecl GetPolicy();
```

### <a name="return-value"></a>戻り値

現在のスケジューラが作成されたポリシーのコピー。

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。

##  <a name="id"></a> id

現在のスケジューラの一意識別子を返します。

```
static unsigned int __cdecl Id();
```

### <a name="return-value"></a>戻り値

スケジューラが呼び出し元のコンテキストでは、そのスケジューラの一意の識別子に関連付けられている場合それ以外の場合、値`-1`します。

### <a name="remarks"></a>Remarks

このメソッドは、呼び出し元のコンテキストが、スケジューラに関連付けられていない場合はスケジューラの添付ファイルには発生しません。

##  <a name="isavailablelocation"></a> IsAvailableLocation

特定の場所は、現在のスケジューラに収録されているかどうかを判断します。

```
static bool __cdecl IsAvailableLocation(const location& _Placement);
```

### <a name="parameters"></a>パラメーター

*(_P)*<br/>
現在のスケジューラのクエリを実行する場所への参照。

### <a name="return-value"></a>戻り値

場所がで指定するかどうかを示す値、`_Placement`引数は、現在のスケジューラを使用できます。

### <a name="remarks"></a>Remarks

このメソッドは、呼び出し元のコンテキストが、スケジューラに関連付けられていない場合はスケジューラの添付ファイルには発生しません。

戻り値は、指定の場所が使用できるかどうかの瞬間的にサンプリングであることに注意してください。 複数のスケジューラが存在する場合は、動的リソースの管理は追加または任意の時点でスケジューラからリソースを剥奪できます。 この場合は、特定の場所は、可用性に変更できます。

##  <a name="registershutdownevent"></a> RegisterShutdownEvent

Windows のイベント ハンドルが渡された原因、`_ShutdownEvent`パラメーターがシグナル状態に、現在のコンテキストに関連付けられているスケジューラがシャット ダウンし、それ自体を破棄します。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドは、複数のシャット ダウン イベントを登録できます。

```
static void __cdecl RegisterShutdownEvent(HANDLE _ShutdownEvent);
```

### <a name="parameters"></a>パラメーター

*_ShutdownEvent*<br/>
現在のコンテキストに関連付けられたスケジューラがシャット ダウンし、それ自体を破棄するときに、ランタイムによって通知される Windows イベント オブジェクトへのハンドル。

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにアタッチされているスケジューラがない場合は、このメソッドを呼び出すことになります、 [scheduler_not_attached](scheduler-not-attached-class.md)例外がスローされます。

##  <a name="scheduletask"></a> ScheduleTask

呼び出し元のコンテキストに関連付けられたスケジューラ内での軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョン`_Placement`タスクが実行指定した位置に重きをさせます。

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

*_Proc*<br/>
軽量タスクの本体を実行するために実行する関数へのポインター。

*_Data*<br/>
タスクの本体にパラメーターとして渡されるデータへの void ポインター。

*(_P)*<br/>
実行中に、軽量タスクをバイアスは場所への参照。

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
