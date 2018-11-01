---
title: Context クラス
ms.date: 11/04/2016
f1_keywords:
- Context
- CONCRT/concurrency::Context
- CONCRT/concurrency::Context::Block
- CONCRT/concurrency::Context::CurrentContext
- CONCRT/concurrency::Context::GetId
- CONCRT/concurrency::Context::GetScheduleGroupId
- CONCRT/concurrency::Context::GetVirtualProcessorId
- CONCRT/concurrency::Context::Id
- CONCRT/concurrency::Context::IsCurrentTaskCollectionCanceling
- CONCRT/concurrency::Context::IsSynchronouslyBlocked
- CONCRT/concurrency::Context::Oversubscribe
- CONCRT/concurrency::Context::ScheduleGroupId
- CONCRT/concurrency::Context::Unblock
- CONCRT/concurrency::Context::VirtualProcessorId
- CONCRT/concurrency::Context::Yield
helpviewer_keywords:
- Context class
ms.assetid: c0d553f3-961d-4ecd-9a29-4fa4351673b8
ms.openlocfilehash: c6b219eabd008114f40401c64465e44607c2ee9b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555078"
---
# <a name="context-class"></a>Context クラス

実行コンテキストの抽象化を表します。

## <a name="syntax"></a>構文

```
class Context;
```

## <a name="members"></a>メンバー

### <a name="protected-constructors"></a>プロテクト コンストラクター

|名前|説明|
|----------|-----------------|
|[~ Context デストラクター](#dtor)||

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ブロック](#block)|現在のコンテキストをブロックします。|
|[CurrentContext](#currentcontext)|現在のコンテキストへのポインターを返します。|
|[GetId](#getid)|コンテキストが属するスケジューラ内で一意のコンテキストの識別子を返します。|
|[GetScheduleGroupId](#getschedulegroupid)|コンテキストが現在実行されているスケジュール グループの識別子を返します。|
|[GetVirtualProcessorId](#getvirtualprocessorid)|コンテキストが現在実行されている仮想プロセッサの識別子を返します。|
|[ID](#id)|現在のコンテキストが属するスケジューラ内で一意の現在のコンテキストの識別子を返します。|
|[IsCurrentTaskCollectionCanceling](#iscurrenttaskcollectioncanceling)|現在のコンテキストで現在インラインで実行されているタスク コレクションがアクティブなキャンセル処理中である (または間もなくキャンセル処理が開始される) かどうかを示す値を返します。|
|[IsSynchronouslyBlocked](#issynchronouslyblocked)|コンテキストが同期的にブロックされているかどうかを判断します。 コンテキストがブロックを引き起こしたアクションを明示的に実行した場合、そのコンテキストは同期的にブロックされていると見なされます。|
|[オーバーサブスク ライブします。](#oversubscribe)|スケジューラの仮想プロセッサのいずれかで実行されるコンテキストで呼び出された場合に、コード ブロックの期間中、追加の仮想プロセッサをそのスケジューラに挿入します。|
|[ScheduleGroupId](#schedulegroupid)|現在のコンテキストが実行されているスケジュール グループの識別子を返します。|
|[ブロック解除します。](#unblock)|コンテキストのブロックを解除し、実行できるようにします。|
|[VirtualProcessorId](#virtualprocessorid)|現在のコンテキストが実行されている仮想プロセッサの識別子を返します。|
|[Yield](#yield)|別のコンテキストが実行できるように実行を譲歩します。 実行の権利を譲る他のコンテキストが存在しない場合、スケジューラによって別のオペレーティング システム スレッドに明け渡されます。|

## <a name="remarks"></a>Remarks

同時実行ランタイム スケジューラ (を参照してください[スケジューラ](scheduler-class.md))、アプリケーションで作業を実行する実行コンテキストを使用してキューに登録されています。 Win32 スレッドは、Windows オペレーティング システムの実行コンテキストの例です。

スケジューラのコンカレンシー レベルは、リソース マネージャーによって許可された仮想プロセッサの数と常に等しくなります。 仮想プロセッサとは、処理リソースを抽象化したものであり、基になるシステムのハードウェア スレッドに対応しています。 指定された時点に 1 つの仮想プロセッサで実行できるスケジューラ コンテキストは 1 つのみです。

スケジューラは本質的に協調的であるため、実行コンテキストが待機状態になると、常に仮想プロセッサを別のコンテキストに渡す可能性があります。 待機状態が終了すると、スケジューラの使用可能な仮想プロセッサが実行を開始するまで再開できません。

## <a name="inheritance-hierarchy"></a>継承階層

`Context`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="block"></a> ブロック

現在のコンテキストをブロックします。

```
static void __cdecl Block();
```

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。

仮想プロセッサが可能性のあるまたはを実行する別の実行可能なコンテキストを検索、呼び出し元のコンテキストが仮想プロセッサで実行している場合、新しく作成します。

後に、`Block`への呼び出しにペアリングする必要があります、メソッドが呼び出されたかが呼び出される、[ブロック解除](#unblock)を再度実行するために別の実行コンテキストからメソッド。 コードが別のスレッドを呼び出すことができるコンテキストを公開ポイントの間で重要な期間があることに注意してください、`Unblock`メソッドと、実際のメソッドの呼び出しポイント`Block`されます。 この期間中、メソッドの順番をブロックおよびブロックを解除する、独自の理由 (たとえば、ロックの取得など) を呼び出さないでください。 呼び出し、`Block`と`Unblock`メソッドは、ブロックおよびブロック解除の理由を追跡しません。 1 つのオブジェクトでの所有権がある、 `Block` -  `Unblock`ペア。

このメソッドが、さまざまな例外をスロー [scheduler_resource_allocation_error](scheduler-resource-allocation-error-class.md)します。

##  <a name="dtor"></a> ~ コンテキスト

```
virtual ~Context();
```

##  <a name="currentcontext"></a> CurrentContext

現在のコンテキストへのポインターを返します。

```
static Context* __cdecl CurrentContext();
```

### <a name="return-value"></a>戻り値

現在のコンテキストへのポインター。

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。

##  <a name="getid"></a> GetId

コンテキストが属するスケジューラ内で一意のコンテキストの識別子を返します。

```
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>戻り値

コンテキストがコンテキストが属するスケジューラ内で一意の識別子。

##  <a name="getschedulegroupid"></a> GetScheduleGroupId

コンテキストが現在実行されているスケジュール グループの識別子を返します。

```
virtual unsigned int GetScheduleGroupId() const = 0;
```

### <a name="return-value"></a>戻り値

コンテキストが現在の作業のスケジュール グループの識別子です。

### <a name="remarks"></a>Remarks

このメソッドからの戻り値は、コンテキストが実行されているスケジュール グループの瞬間的にサンプリングします。 このメソッドは、現在のコンテキスト以外のコンテキストで呼び出されると、値は古い時点が返され、に依存できません。 通常、このメソッドは、デバッグやトレースの目的でのみ使用されます。

##  <a name="getvirtualprocessorid"></a> GetVirtualProcessorId

コンテキストが現在実行されている仮想プロセッサの識別子を返します。

```
virtual unsigned int GetVirtualProcessorId() const = 0;
```

### <a name="return-value"></a>戻り値

コンテキストは、現在のコンテキストは、現在; で実行されている仮想プロセッサの識別子の仮想プロセッサで実行されている場合それ以外の場合、値`-1`します。

### <a name="remarks"></a>Remarks

このメソッドからの戻り値は、コンテキストが実行されている仮想プロセッサの瞬間的にサンプリングします。 この値は古い時点が返され、に依存できません。 通常、このメソッドは、デバッグやトレースの目的でのみ使用されます。

##  <a name="id"></a> id

現在のコンテキストが属するスケジューラ内で一意の現在のコンテキストの識別子を返します。

```
static unsigned int __cdecl Id();
```

### <a name="return-value"></a>戻り値

現在のコンテキストが、現在のコンテキストを現在のコンテキストが属するスケジューラ内で一意の識別子のスケジューラにアタッチされている場合それ以外の場合、値`-1`します。

##  <a name="iscurrenttaskcollectioncanceling"></a> IsCurrentTaskCollectionCanceling

現在のコンテキストで現在インラインで実行されているタスク コレクションがアクティブなキャンセル処理中である (または間もなくキャンセル処理が開始される) かどうかを示す値を返します。

```
static bool __cdecl IsCurrentTaskCollectionCanceling();
```

### <a name="return-value"></a>戻り値

呼び出し元のコンテキストにスケジューラがアタッチされているタスク グループがそのコンテキストでタスクをインラインを実行する場合は、かどうかを示す値そのタスク グループは、アクティブなキャンセル処理 (またはいたします);それ以外の場合、値`false`します。

##  <a name="issynchronouslyblocked"></a> IsSynchronouslyBlocked

コンテキストが同期的にブロックされているかどうかを判断します。 コンテキストがブロックを引き起こしたアクションを明示的に実行した場合、そのコンテキストは同期的にブロックされていると見なされます。

```
virtual bool IsSynchronouslyBlocked() const = 0;
```

### <a name="return-value"></a>戻り値

コンテキストが同期的にブロックされているかどうか。

### <a name="remarks"></a>Remarks

コンテキストがブロックを引き起こしたアクションを明示的に実行した場合、そのコンテキストは同期的にブロックされていると見なされます。 スレッドのスケジューラ上への直接呼び出しを示すこれは、`Context::Block`メソッドまたは同期オブジェクトを使用して構築された、`Context::Block`メソッド。

このメソッドからの戻り値は、コンテキストが同期的にブロックされているかどうかの瞬間的な例です。 この値は、時点が返され、非常に特定の状況でのみ使用できますが古い可能性がありますに。

##  <a name="operator_delete"></a> delete 演算子

A`Context`オブジェクトは、ランタイムによって内部的に破棄されます。 明示的に削除できません。

```
void operator delete(void* _PObject);
```

### <a name="parameters"></a>パラメーター

*_PObject*<br/>
削除するオブジェクトへのポインター。

##  <a name="oversubscribe"></a> オーバーサブスク ライブします。

スケジューラの仮想プロセッサのいずれかで実行されるコンテキストで呼び出された場合に、コード ブロックの期間中、追加の仮想プロセッサをそのスケジューラに挿入します。

```
static void __cdecl Oversubscribe(bool _BeginOversubscription);
```

### <a name="parameters"></a>パラメーター

*_BeginOversubscription*<br/>
場合**true**を示す値、オーバー サブスクリプションの期間中、追加の仮想プロセッサを追加する必要があります。 場合**false**を示す値、オーバー サブスクリプションが終了する必要があります、以前に追加の仮想プロセッサを削除する必要があります。

##  <a name="schedulegroupid"></a> ScheduleGroupId

現在のコンテキストが実行されているスケジュール グループの識別子を返します。

```
static unsigned int __cdecl ScheduleGroupId();
```

### <a name="return-value"></a>戻り値

場合は、現在のコンテキストが動作して、現在のコンテキストが、スケジューラにアタッチされ、スケジュール グループに取り組んで、スケジューラの識別子をグループそれ以外の場合、値`-1`します。

##  <a name="unblock"></a> ブロック解除します。

コンテキストのブロックを解除し、実行できるようにします。

```
virtual void Unblock() = 0;
```

### <a name="remarks"></a>Remarks

呼び出すのために区切れば、`Unblock`メソッドに対応する呼び出しの前に、[ブロック](#block)メソッド。 呼び出す限り、`Block`と`Unblock`メソッドが正しくペアになっている、ランタイムが適切に自然な順序の競合を処理します。 `Unblock`前に、の呼び出しを`Block`呼び出しの影響を単に無効に、`Block`呼び出します。

いくつかの例外がこのメソッドからスローされる可能性があります。 コンテキストが呼び出しを試みると、`Unblock`メソッド自体、 [context_self_unblock](context-self-unblock-class.md)例外がスローされます。 場合への呼び出し`Block`と`Unblock`正しくペアになっていない (たとえば、2 回の呼び出しに`Unblock`が現在実行されているコンテキストが行われます)、 [context_unblock_unbalanced](context-unblock-unbalanced-class.md)例外がスローされます。

コードが別のスレッドを呼び出すことができるコンテキストを公開ポイントの間で重要な期間があることに注意してください、`Unblock`メソッドと、実際のメソッドの呼び出しポイント`Block`されます。 この期間中、メソッドの順番をブロックおよびブロックを解除する、独自の理由 (たとえば、ロックの取得など) を呼び出さないでください。 呼び出し、`Block`と`Unblock`メソッドは、ブロックおよびブロック解除の理由を追跡しません。 1 つのオブジェクトでの所有権がある、`Block`と`Unblock`ペア。

##  <a name="virtualprocessorid"></a> VirtualProcessorId

現在のコンテキストが実行されている仮想プロセッサの識別子を返します。

```
static unsigned int __cdecl VirtualProcessorId();
```

### <a name="return-value"></a>戻り値

現在のコンテキストが、現在のコンテキストが; で実行されている仮想プロセッサの識別子のスケジューラにアタッチされている場合それ以外の場合、値`-1`します。

### <a name="remarks"></a>Remarks

このメソッドから戻り値では、現在のコンテキストが実行されている仮想プロセッサの瞬間的にサンプリングです。 この値は古い時点が返され、に依存できません。 通常、このメソッドは、デバッグやトレースの目的でのみ使用されます。

##  <a name="yield"></a> yield

別のコンテキストが実行できるように実行を譲歩します。 実行の権利を譲る他のコンテキストが存在しない場合、スケジューラによって別のオペレーティング システム スレッドに明け渡されます。

```
static void __cdecl Yield();
```

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。

##  <a name="yieldexecution"></a> YieldExecution

別のコンテキストが実行できるように実行を譲歩します。 実行の権利を譲る他のコンテキストが存在しない場合、スケジューラによって別のオペレーティング システム スレッドに明け渡されます。

```
static void __cdecl YieldExecution();
```

### <a name="remarks"></a>Remarks

呼び出し元のコンテキストにスケジューラが現在関連付けられていない場合、このメソッドを呼び出すと、プロセスの既定のスケジューラが作成されるか、または呼び出し元コンテキストにアタッチされます。

この関数は、Visual Studio 2015 の新機能と同一である、 [Yield](#yield)機能しますが、Windows.h の Yield マクロと競合しません。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[Scheduler クラス](scheduler-class.md)<br/>
[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)

