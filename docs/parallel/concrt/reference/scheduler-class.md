---
title: Scheduler クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- Scheduler class
ms.assetid: 34cf7961-048d-4852-8a5c-a32f823e3506
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 97abec33d5fa4b372bc26874fd37397a2b78bb29
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
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
|[スケジューラ](#ctor)|オブジェクト、`Scheduler`クラスは、だけのファクトリ メソッドを使用して作成されたことができます。 または暗黙的にします。|  
|[~ Scheduler デストラクター](#dtor)|オブジェクト、`Scheduler`に対するすべての外部参照を停止が存在するときに暗黙的にクラスは破棄されます。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[添付](#attach)|呼び出し元のコンテキストにスケジューラをアタッチします。 このメソッドから制御が戻た後は、呼び出し元のコンテキストは、スケジューラによって管理され、スケジューラは、現在のスケジューラになります。|  
|[作成します。](#create)|動作が説明されている、新しいスケジューラを作成、`_Policy`パラメーターは、スケジューラに初期の参照を配置し、ポインターを返します。|  
|[CreateScheduleGroup](#createschedulegroup)|オーバーロードされます。 スケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョンで`_Placement`により、そのパラメーターで指定された場所で実行する方向に偏ってするを新しく作成されたスケジュール グループ内のタスクです。|  
|[GetNumberOfVirtualProcessors](#getnumberofvirtualprocessors)|スケジューラの仮想プロセッサの現在の数を返します。|  
|[GetPolicy](#getpolicy)|スケジューラの作成に使用されたポリシーのコピーを返します。|  
|[Id](#id)|スケジューラの一意の識別子を返します。|  
|[IsAvailableLocation](#isavailablelocation)|指定された場所が、スケジューラで使用できるかどうかを判断します。|  
|[参照](#reference)|スケジューラの参照カウントをインクリメントします。|  
|[RegisterShutdownEvent](#registershutdownevent)|Windows イベント ハンドルが渡された原因、`_Event`シグナル状態になるスケジューラがシャット ダウンし、それ自体を破棄するときのパラメーターです。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドでは、複数のシャット ダウン イベントを登録できます。|  
|[Release](#release)|スケジュールの参照カウントをデクリメントします。|  
|[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)|既定のスケジューラ ポリシーをランタイムの既定値にリセットします。 既定のスケジューラが作成されると、[次へ] の時刻に、実行時の既定のポリシー設定が使用されます。|  
|[ScheduleTask](#scheduletask)|オーバーロードされます。 スケジューラ内の軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョンで`_Placement`するが優先される指定した場所に実行するためにタスクをさせます。|  
|[SetDefaultSchedulerPolicy](#setdefaultschedulerpolicy)|既定のスケジューラを作成するために使用するユーザー定義のポリシーを使用します。 プロセス内で既定のスケジューラが存在しない場合にのみ、このメソッドを呼び出すことができます。 か、[次へ] の有効な呼び出しまで有効になります、既定のポリシーを設定すると、後に、`SetDefaultSchedulerPolicy`または[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)メソッドです。|  
  
## <a name="remarks"></a>コメント  
 同時実行ランタイム スケジューラ スレッドなど、オペレーティング システムの実行コンテキストにマップされる実行コンテキストを使用して、作業を実行するキューに登録されて、アプリケーションにします。 いつでもは、スケジューラの同時実行レベルは、リソース マネージャーによって許可された仮想プロセッサの数と同じです。 仮想プロセッサとは、処理リソースを抽象化したものであり、基になるシステムのハードウェア スレッドに対応しています。 指定された時点に 1 つの仮想プロセッサで実行できるスケジューラ コンテキストは 1 つのみです。  
  
 同時実行ランタイムでは、1 つのプロセスを並列処理を実行する既定のスケジューラを作成します。 さらに、独自のスケジューラ インスタンスを作成し、このクラスを使用して操作できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Scheduler`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="attach"></a> アタッチ 

 呼び出し元のコンテキストにスケジューラをアタッチします。 このメソッドから制御が戻た後は、呼び出し元のコンテキストは、スケジューラによって管理され、スケジューラは、現在のスケジューラになります。  
  
```
virtual void Attach() = 0;
```  
  
### <a name="remarks"></a>コメント  
 スケジューラでの参照を配置するスケジューラを暗黙的にアタッチします。  
  
 ある時点で、将来、呼び出す必要があります、 [currentscheduler::detach](currentscheduler-class.md#detach)メソッド、スケジューラをシャット ダウンを実行できるようにします。  
  
 このメソッドは既に別のスケジューラにアタッチされているコンテキストから呼び出されると、既存のスケジューラが、以前のスケジューラとして記憶し、新しく作成されたスケジューラは、現在のスケジューラになります。 呼び出すと、`CurrentScheduler::Detach`後で、前のスケジューラのメソッドは、現在のスケジューラとして復元されます。  
  
 このメソッドはスロー、 [improper_scheduler_attach](improper-scheduler-attach-class.md)このスケジューラは、現在のスケジューラで呼び出し元のコンテキストの場合に例外です。  
  
##  <a name="create"></a> 作成します。 

 動作が説明されている、新しいスケジューラを作成、`_Policy`パラメーターは、スケジューラに初期の参照を配置し、ポインターを返します。  
  
```
static Scheduler* __cdecl Create(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Policy`  
 スケジューラ ポリシーを新しく作成されたスケジューラの動作について説明します。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたスケジューラへのポインター。 これは、`Scheduler`オブジェクトには、初期の参照カウントを配置します。  
  
### <a name="remarks"></a>コメント  
 スケジューラの作成後、`Create`メソッドを呼び出す必要があります、`Release`初期の参照カウントを削除して、スケジューラをシャット ダウンを許可するために、今後のいつかメソッドです。  
  
 このメソッドで作成されたスケジューラは、呼び出し元のコンテキストにアタッチされていません。 使用してコンテキストに関連付けることができます、[アタッチ](#attach)メソッドです。  
  
 このメソッドを含む、例外のさまざまな[scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)と[invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md)です。  
  
##  <a name="createschedulegroup"></a> CreateScheduleGroup 

 スケジューラ内で新しいスケジュール グループを作成します。 パラメーターを受け取るバージョンで`_Placement`により、そのパラメーターで指定された場所で実行する方向に偏ってするを新しく作成されたスケジュール グループ内のタスクです。  
  
```
virtual ScheduleGroup* CreateScheduleGroup() = 0;

virtual ScheduleGroup* CreateScheduleGroup(location& _Placement) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Placement`  
 ここで、スケジュール グループ内のタスクが対でを実行する場所への参照。  
  
### <a name="return-value"></a>戻り値  
 新しく作成されたスケジュール グループへのポインター。 これは、`ScheduleGroup`オブジェクトには、初期の参照カウントを配置します。  
  
### <a name="remarks"></a>コメント  
 呼び出す必要があります、[リリース](schedulegroup-class.md#release)作業のスケジュールを実行するときに、スケジュール グループのメソッドです。 スケジュールをスケジューラが破棄されますが、すべての作業キューに登録されている場合は、グループの完了します。  
  
 このスケジューラを明示的に作成した場合は、スケジューラの参照を解放する前に、内のグループのスケジュールへのすべての参照を解放する必要がありますに注意してください。  
  
##  <a name="getnumberofvirtualprocessors"></a> GetNumberOfVirtualProcessors 

 スケジューラの仮想プロセッサの現在の数を返します。  
  
```
virtual unsigned int GetNumberOfVirtualProcessors() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 現在のスケジューラの仮想プロセッサの数。  
  
##  <a name="getpolicy"></a> GetPolicy 

 スケジューラの作成に使用されたポリシーのコピーを返します。  
  
```
virtual SchedulerPolicy GetPolicy() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラの作成に使用されたポリシーのコピー。  
  
##  <a name="id"></a> id 

 スケジューラの一意の識別子を返します。  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラの一意の識別子。  
  
##  <a name="isavailablelocation"></a> IsAvailableLocation 

 指定された場所が、スケジューラで使用できるかどうかを判断します。  
  
```
virtual bool IsAvailableLocation(const location& _Placement) const = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Placement`  
 スケジューラのクエリを実行する場所への参照。  
  
### <a name="return-value"></a>戻り値  
 場所がで指定するかどうかを示す、`_Placement`引数は、スケジューラを使用できます。  
  
### <a name="remarks"></a>コメント  
 戻り値が指定された場所が使用できるかどうかの瞬間的にサンプリングに注意してください。 複数のスケジューラが存在する場合は、動的なリソース管理は追加または任意の時点でスケジューラからリソースを取り去ることがことができます。 この場合は、指定された場所は、可用性に変更できます。  
  
##  <a name="reference"></a> 参照 

 スケジューラの参照カウントをインクリメントします。  
  
```
virtual unsigned int Reference() = 0 ;
```  
  
### <a name="return-value"></a>戻り値  
 新たにインクリメントされた参照カウントします。  
  
### <a name="remarks"></a>コメント  
 これは、スケジューラの構成の有効期間を管理に通常使用されます。 するの参照カウントを 0 にスケジューラが、スケジューラがシャット ダウン自体破壊すべて機能、スケジューラが完了しました。  
  
 メソッドがスローされます、 [improper_scheduler_reference](improper-scheduler-reference-class.md)例外の場合は、参照カウントを呼び出す前に、`Reference`メソッドは 0 で、スケジューラが所有していないコンテキストから呼び出しが行われます。  
  
##  <a name="registershutdownevent"></a> RegisterShutdownEvent 

 Windows イベント ハンドルが渡された原因、`_Event`シグナル状態になるスケジューラがシャット ダウンし、それ自体を破棄するときのパラメーターです。 イベントがシグナル状態に、スケジューラにスケジュールされていたすべての作業が完了しました。 このメソッドでは、複数のシャット ダウン イベントを登録できます。  
  
```
virtual void RegisterShutdownEvent(HANDLE _Event) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Event`  
 スケジューラがシャット ダウンし、それ自体を破棄するときに、ランタイムによって通知される Windows イベント オブジェクトへのハンドル。  
  
##  <a name="release"></a> リリース 

 スケジュールの参照カウントをデクリメントします。  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 新たにデクリメントされた参照カウントします。  
  
### <a name="remarks"></a>コメント  
 これは、スケジューラの構成の有効期間を管理に通常使用されます。 するの参照カウントを 0 にスケジューラが、スケジューラがシャット ダウン自体破壊すべて機能、スケジューラが完了しました。  
  
##  <a name="resetdefaultschedulerpolicy"></a> ResetDefaultSchedulerPolicy 

 既定のスケジューラ ポリシーをランタイムの既定値にリセットします。 既定のスケジューラが作成されると、[次へ] の時刻に、実行時の既定のポリシー設定が使用されます。  
  
```
static void __cdecl ResetDefaultSchedulerPolicy();
```  
  
### <a name="remarks"></a>コメント  
 プロセス内で、既定のスケジューラが存在する間、このメソッドを呼び出すことができます。 既存の既定のスケジューラのポリシーには影響しません。 ただし場合は、既定のスケジューラがシャット ダウンして、新しい既定値は、後で作成するが、新しいスケジューラはランタイムの既定のポリシー設定を使用します。  
  
##  <a name="ctor"></a> スケジューラ 

 オブジェクト、`Scheduler`クラスは、だけのファクトリ メソッドを使用して作成されたことができます。 または暗黙的にします。  
  
```
Scheduler();
```  
  
### <a name="remarks"></a>コメント  
 プロセスの既定のスケジューラが、多くの呼び出し元のコンテキストにアタッチされているスケジューラを必要とするランタイム関数を使用するとき暗黙的に作成されます。 内のメソッド、`CurrentScheduler`クラスと、PPL とエージェントのレイヤーの機能は通常暗黙的な添付ファイルを実行します。  
  
 いずれかで明示的にスケジューラを作成することも、`CurrentScheduler::Create`メソッドまたは`Scheduler::Create`メソッドです。  
  
##  <a name="dtor"></a> ~ スケジューラ 

 オブジェクト、`Scheduler`に対するすべての外部参照を停止が存在するときに暗黙的にクラスは破棄されます。  
  
```
virtual ~Scheduler();
```  
  
##  <a name="scheduletask"></a> ScheduleTask 

 スケジューラ内の軽量タスクをスケジュールします。 軽量タスクは、ランタイムによって決定スケジュール グループに配置されます。 パラメーターを受け取るバージョンで`_Placement`するが優先される指定した場所に実行するためにタスクをさせます。  
  
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
 `_Proc`  
 軽量タスクの本体を実行するために実行する関数へのポインター。  
  
 `_Data`  
 タスクの本体にパラメーターとして渡されるデータへの void ポインターです。  
  
 `_Placement`  
 実行する方向には、軽量タスクをバイアスは場所への参照。  
  
##  <a name="setdefaultschedulerpolicy"></a> SetDefaultSchedulerPolicy 

 既定のスケジューラを作成するために使用するユーザー定義のポリシーを使用します。 プロセス内で既定のスケジューラが存在しない場合にのみ、このメソッドを呼び出すことができます。 か、[次へ] の有効な呼び出しまで有効になります、既定のポリシーを設定すると、後に、`SetDefaultSchedulerPolicy`または[ResetDefaultSchedulerPolicy](#resetdefaultschedulerpolicy)メソッドです。  
  
```
static void __cdecl SetDefaultSchedulerPolicy(const SchedulerPolicy& _Policy);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Policy`  
 既定のスケジューラ ポリシーとして設定するポリシー。  
  
### <a name="remarks"></a>コメント  
 場合、`SetDefaultSchedulerPolicy`メソッドは、プロセス内で、既定のスケジューラが既に存在する場合、ランタイムがスローされます、 [default_scheduler_exists](default-scheduler-exists-class.md)例外。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [Scheduler クラス](scheduler-class.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



