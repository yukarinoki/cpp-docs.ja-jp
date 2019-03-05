---
title: Scheduler クラス
ms.date: 11/04/2016
f1_keywords:
- Scheduler
- CONCRT/concurrency::Scheduler
- CONCRT/concurrency::Scheduler::Scheduler
- CONCRT/concurrency::Scheduler::Attach
- CONCRT/concurrency::Scheduler::Create
- CONCRT/concurrency::Scheduler::CreateScheduleGroup
- CONCRT/concurrency::Scheduler::GetNumberOfVirtualProcessors
- CONCRT/concurrency::Scheduler::GetPolicy
- CONCRT/concurrency::Scheduler::Id
- CONCRT/concurrency::Scheduler::IsAvailableLocation
- CONCRT/concurrency::Scheduler::Reference
- CONCRT/concurrency::Scheduler::RegisterShutdownEvent
- CONCRT/concurrency::Scheduler::Release
- CONCRT/concurrency::Scheduler::ResetDefaultSchedulerPolicy
- CONCRT/concurrency::Scheduler::ScheduleTask
- CONCRT/concurrency::Scheduler::SetDefaultSchedulerPolicy
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
ms.openlocfilehash: f27dace61b0764962a78695c2a4c6b180b09d7a3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287903"
---
# <a name="scheduler-class"></a>Scheduler クラス

同時実行ランタイム スケジューラの抽象化を表します。

## <a name="syntax"></a>構文

```
class Scheduler;
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[スケジューラ](#ctor)|オブジェクト、`Scheduler`工場出荷時のメソッドを使用して作成できるクラスまたは暗黙的にします。|
|[~ Scheduler デストラクター](#dtor)|オブジェクト、`Scheduler`へのすべての外部参照が存在しないときに暗黙的にクラスが破棄されます。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[Attach](#attach)|呼び出し元のコンテキストにスケジューラをアタッチします。 このメソッドから制御が戻た後は、呼び出し元のコンテキストは、スケジューラによって管理され、スケジューラは、現在のスケジューラになります。|
|[作成します。](#create)|動作が説明されている新しいスケジューラを作成、`_Policy`パラメーターは、スケジューラに最初の参照を配置し、ポインターを返します。|
|[CreateScheduleGroup](#createschedulegroup)|オーバーロードされます。 スケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョン`_Placement`にそのパラメーターで指定された場所で実行に偏っていますが、新しく作成したスケジュール グループ内のタスクが原因です。|
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|スケジューラの仮想プロセッサの現在の数を返します。|
|[GetPolicy](#getpolicy)|スケジューラが作成されたポリシーのコピーを返します。|
|[ID](#id)|スケジューラの一意識別子を返します。|
|[IsAvailableLocation](#isavailablelocation)|特定の場所は、スケジューラに収録されているかどうかを判断します。|
|[参照](#reference)|スケジューラの参照カウントをインクリメントします。|
|[RegisterShutdownEvent](#registershutdownevent)|Windows のイベント ハンドルが渡された原因、`_Event`パラメーターがシグナル状態にスケジューラがシャット ダウンし、それ自体を破棄します。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドは、複数のシャット ダウン イベントを登録できます。|
|[Release](#release)|スケジューラの参照カウントをデクリメントします。|
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|既定のスケジューラ ポリシーをランタイムの既定値にリセットします。 [次へ] には、既定のスケジューラの作成時に、ランタイムの既定のポリシー設定が使用されます。|
|[ScheduleTask](#scheduletask)|オーバーロードされます。 スケジューラ内での軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョン`_Placement`タスクが実行指定した位置に重きをさせます。|
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|既定のスケジューラの作成に使用するユーザー定義ポリシーを許可します。 プロセス内での既定のスケジューラが存在しない場合にのみ、このメソッドを呼び出すことができます。 か、[次へ] の有効な呼び出しまで有効になります、既定のポリシーを設定した後、`SetDefaultSchedulerPolicy`または[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)メソッド。|

## <a name="remarks"></a>Remarks

同時実行ランタイム スケジューラは、スレッドなど、オペレーティング システムの実行コンテキストにマップされる実行コンテキストを使用して、アプリケーションでそれをキューに作業を実行します。 いつでも、スケジューラの同時実行レベル、リソース マネージャーによって許可された仮想プロセッサの数に等しくなります。 仮想プロセッサとは、処理リソースを抽象化したものであり、基になるシステムのハードウェア スレッドに対応しています。 指定された時点に 1 つの仮想プロセッサで実行できるスケジューラ コンテキストは 1 つのみです。

同時実行ランタイムでは、1 つのプロセス並列処理を実行する既定のスケジューラを作成します。 さらに、独自のスケジューラ インスタンスを作成して、このクラスを使用してを操作することができます。

## <a name="inheritance-hierarchy"></a>継承階層

`Scheduler`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="attach"></a> アタッチ

呼び出し元のコンテキストにスケジューラをアタッチします。 このメソッドから制御が戻た後は、呼び出し元のコンテキストは、スケジューラによって管理され、スケジューラは、現在のスケジューラになります。

```
virtual void Attach() = 0;
```

### <a name="remarks"></a>Remarks

参照をスケジューラに配置するスケジューラを暗黙的にアタッチします。

ある時点で、後で呼び出す必要があります、 [currentscheduler::detach](currentscheduler-class.md#detach)メソッドは、スケジューラをシャット ダウンできるようにします。

このメソッドは既に別のスケジューラにアタッチされているコンテキストから呼び出されると、既存のスケジューラは、以前のスケジューラとして記憶し、新しく作成されたスケジューラが現在のスケジューラになります。 呼び出すと、`CurrentScheduler::Detach`メソッドは、後で、前のスケジューラは、現在のスケジューラとして復元されます。

このメソッドがスローされます、 [improper_scheduler_attach](improper-scheduler-attach-class.md)このスケジューラは、呼び出し元のコンテキストの現在のスケジューラの場合は例外です。

##  <a name="create"></a> 作成します。

動作が説明されている新しいスケジューラを作成、`_Policy`パラメーターは、スケジューラに最初の参照を配置し、ポインターを返します。

```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>パラメーター

*_Policy*<br/>
スケジューラ ポリシーを新しく作成されたスケジューラの動作について説明します。

### <a name="return-value"></a>戻り値

新しく作成されたスケジューラへのポインター。 これは、`Scheduler`オブジェクトが配置される最初の参照数。

### <a name="remarks"></a>Remarks

スケジューラの作成後、`Create`メソッドを呼び出す必要があります、`Release`初期の参照カウントを削除して、スケジューラをシャット ダウンを許可するのには、今後ある時点でのメソッド。

このメソッドで作成されたスケジューラは、呼び出し元のコンテキストにアタッチされていません。 使用してコンテキストに関連付けることができます、[アタッチ](#attach)メソッド。

このメソッドが、さまざまな例外をスロー [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)と[invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)します。

##  <a name="createschedulegroup"></a> CreateScheduleGroup

スケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョン`_Placement`にそのパラメーターで指定された場所で実行に偏っていますが、新しく作成したスケジュール グループ内のタスクが原因です。

```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```

### <a name="parameters"></a>パラメーター

*(_P)*<br/>
場所のスケジュール グループ内のタスクが強まりますでを実行する場所への参照。

### <a name="return-value"></a>戻り値

新しく作成したスケジュール グループへのポインター。 これは、`ScheduleGroup`オブジェクトが配置される最初の参照数。

### <a name="remarks"></a>Remarks

呼び出す必要があります、[リリース](schedulegroup-class.md#release)作業のスケジュールを実行するときに、スケジュール グループのメソッド。 スケジューラでスケジュールを破棄グループにすべての作業がキューに置かれたときに完了します。

このスケジューラを明示的に作成した場合は、スケジューラの参照を解放する前に、内のグループのスケジュールへのすべての参照を解放する必要がありますに注意してください。

##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors

スケジューラの仮想プロセッサの現在の数を返します。

```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```

### <a name="return-value"></a>戻り値

現在のスケジューラの仮想プロセッサ数。

##  <a name="getpolicy"></a> GetPolicy

スケジューラが作成されたポリシーのコピーを返します。

```
virtual SchedulerPolicy GetPolicy() const = 0;
```

### <a name="return-value"></a>戻り値

スケジューラが作成されたポリシーのコピー。

##  <a name="id"></a> id

スケジューラの一意識別子を返します。

```
virtual unsigned int Id() const = 0;
```

### <a name="return-value"></a>戻り値

スケジューラの一意の識別子。

##  <a name="isavailablelocation"></a> IsAvailableLocation

特定の場所は、スケジューラに収録されているかどうかを判断します。

```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```

### <a name="parameters"></a>パラメーター

*(_P)*<br/>
スケジューラのクエリを実行する場所への参照。

### <a name="return-value"></a>戻り値

場所がで指定するかどうかを示す値、`_Placement`引数は、スケジューラを使用できます。

### <a name="remarks"></a>Remarks

戻り値は、指定の場所が使用できるかどうかの瞬間的にサンプリングであることに注意してください。 複数のスケジューラが存在する場合は、動的リソースの管理は追加または任意の時点でスケジューラからリソースを剥奪できます。 この場合は、特定の場所は、可用性に変更できます。

##  <a name="reference"></a> 参照

スケジューラの参照カウントをインクリメントします。

```
virtual unsigned int Reference() = 0 ;
```

### <a name="return-value"></a>戻り値

新たにインクリメントされた参照の数。

### <a name="remarks"></a>Remarks

これは、スケジューラの構成の有効期間を管理に通常使用します。 参照数を 0 にスケジューラが、スケジューラはシャット ダウンとデストラクション自体は結局、スケジューラで作業が完了しました。

メソッドがスローされます、 [improper_scheduler_reference](improper-scheduler-reference-class.md)呼び出す前に、参照をカウントする場合は例外、`Reference`メソッドは 0 で、スケジューラによって所有されていないコンテキストから呼び出しが行われます。

##  <a name="registershutdownevent"></a> RegisterShutdownEvent

Windows のイベント ハンドルが渡された原因、`_Event`パラメーターがシグナル状態にスケジューラがシャット ダウンし、それ自体を破棄します。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドは、複数のシャット ダウン イベントを登録できます。

```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```

### <a name="parameters"></a>パラメーター

*_Event*<br/>
スケジューラがシャット ダウンし、それ自体を破棄するときに、ランタイムによって通知される Windows イベント オブジェクトへのハンドル。

##  <a name="release"></a> リリース

スケジューラの参照カウントをデクリメントします。

```
virtual unsigned int Release() = 0;
```

### <a name="return-value"></a>戻り値

新たにデクリメントされた参照の数。

### <a name="remarks"></a>Remarks

これは、スケジューラの構成の有効期間を管理に通常使用します。 参照数を 0 にスケジューラが、スケジューラはシャット ダウンとデストラクション自体は結局、スケジューラで作業が完了しました。

##  <a name="resetdefaultschedulerpolicy"></a> ResetDefaultSchedulerPolicy

既定のスケジューラ ポリシーをランタイムの既定値にリセットします。 [次へ] には、既定のスケジューラの作成時に、ランタイムの既定のポリシー設定が使用されます。

```
static void __cdecl ResetDefaultSchedulerPolicy();
```

### <a name="remarks"></a>Remarks

既定のスケジューラが、プロセス内に存在している間、このメソッドを呼び出すことができます。 既存の既定のスケジューラのポリシーは影響しません。 ただし場合は、既定のスケジューラがシャット ダウンして、新しい既定値は、後で作成された、新しいスケジューラはランタイムの既定のポリシー設定を使用します。

##  <a name="ctor"></a> スケジューラ

オブジェクト、`Scheduler`工場出荷時のメソッドを使用して作成できるクラスまたは暗黙的にします。

```
Scheduler();
```

### <a name="remarks"></a>Remarks

プロセスの既定のスケジューラは、多くの呼び出し元のコンテキストにアタッチするためのスケジューラを必要とするランタイム関数を使用するとき暗黙的に作成されます。 内のメソッド、`CurrentScheduler`クラスと、PPL とエージェントのレイヤーの機能は通常暗黙的な添付ファイルを実行します。

いずれかで明示的にスケジューラを作成することも、`CurrentScheduler::Create`メソッドまたは`Scheduler::Create`メソッド。

##  <a name="dtor"></a> ~ スケジューラ

オブジェクト、`Scheduler`へのすべての外部参照が存在しないときに暗黙的にクラスが破棄されます。

```
virtual ~Scheduler();
```

##  <a name="scheduletask"></a> ScheduleTask

スケジューラ内での軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョン`_Placement`タスクが実行指定した位置に重きをさせます。

```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;

virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data,
    location& _Placement) = 0;
```

### <a name="parameters"></a>パラメーター

*_Proc*<br/>
軽量タスクの本体を実行するために実行する関数へのポインター。

*_Data*<br/>
タスクの本体にパラメーターとして渡されるデータへの void ポインター。

*(_P)*<br/>
実行中に、軽量タスクをバイアスは場所への参照。

##  <a name="setdefaultschedulerpolicy"></a> SetDefaultSchedulerPolicy

既定のスケジューラの作成に使用するユーザー定義ポリシーを許可します。 プロセス内での既定のスケジューラが存在しない場合にのみ、このメソッドを呼び出すことができます。 か、[次へ] の有効な呼び出しまで有効になります、既定のポリシーを設定した後、`SetDefaultSchedulerPolicy`または[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)メソッド。

```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```

### <a name="parameters"></a>パラメーター

*_Policy*<br/>
既定のスケジューラ ポリシーとして設定するポリシー。

### <a name="remarks"></a>Remarks

場合、`SetDefaultSchedulerPolicy`メソッドが呼び出されたは、プロセス内で、既定のスケジューラが既に存在する場合、ランタイムがスローされます、 [default_scheduler_exists](default-scheduler-exists-class.md)例外。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)<br/>
[PolicyElementKey](concurrency-namespace-enums.md)<br/>
[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
