---
title: task_group クラス
ms.date: 07/20/2018
f1_keywords:
- task_group
- PPL/concurrency::task_group
- PPL/concurrency::task_group::task_group
helpviewer_keywords:
- task_group class
ms.openlocfilehash: 545b368b3042da74a42db5a6ea30e97054d5fd03
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294136"
---
# <a name="taskgroup-class"></a>task_group クラス

`task_group` クラスは、待機または取り消しができる並列処理のコレクションを表します。

## <a name="syntax"></a>構文

```
class task_group;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[task_group](#ctor)|オーバーロードされます。 新しい `task_group` オブジェクトを構築します。|
|[~ task_group デストラクター](#dtor)|`task_group` オブジェクトを破棄します。 呼び出すか、予想される、`wait`または`run_and_wait`実行する前に、デストラクター、デストラクターがスタック アンワインドにより例外結果として実行しない限り、オブジェクトのメソッド。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[cancel](#cancel)|このタスク グループをルートとする作業のサブツリーの取り消しを試行する最善の努力は、します。 タスク グループでスケジュールのすべてのタスクはキャンセル推移的に可能な場合。|
|[is_canceling](#is_canceling)|かどうか、タスク グループは現在キャンセル中、呼び出し元に通知します。 これは必ずしもを`cancel`でメソッドが呼び出された、`task_group`オブジェクト (もちろんを返すには、このメソッドを修飾などが`true`)。 ケースがある可能性があります`task_group`オブジェクトはインラインで実行し、さらに、タスク グループを作業ツリーが取り消されました。 これらの場所などの場合、ランタイムがキャンセルは、このフローは前もって確認できます`task_group`オブジェクト、`true`も返されます。|
|[run](#run)|オーバーロードされます。 タスクをスケジュール、`task_group`オブジェクト。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run`の有効期間を管理するため、呼び出し元は、`task_handle`オブジェクト。 バージョンのパラメーターは、可能性のあるランタイム内でヒープ割り当て関数のオブジェクトへの参照を受け取るメソッドへの参照を受け取るバージョンを使用してより適切に機能しないの実行、`task_handle`オブジェクト。 パラメーターを受け取るバージョン`_Placement`タスクがそのパラメーターで指定された場所を実行して重きをさせます。|
|[run_and_wait](#run_and_wait)|オーバーロードされます。 呼び出し元のコンテキストでのインラインを実行するタスクをスケジュール、`task_group`オブジェクトの完全なキャンセルのサポート。 すべての作業になるまでにその後、関数が待機、`task_group`オブジェクトが完了したか取り消されました。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run_and_wait`の有効期間を管理するため、呼び出し元は、`task_handle`オブジェクト。|
|[wait](#wait)|すべての作業になるまでの待機、`task_group`オブジェクトが完了したか取り消されました。|

## <a name="remarks"></a>Remarks

異なり、大きく制限された`structured_task_group`クラス、`task_group`クラスより一般的な構成要素。 任意で説明されている制限のない[structured_task_group](structured-task-group-class.md)します。 `task_group` オブジェクトをスレッド間で使用される安全かつ自由形式の方法で使用される可能性があります。 欠点、`task_group`コンス トラクターは、実行がされていないことだけでなく`structured_task_group`の少量の作業を実行するタスクを作成します。

詳細については、次を参照してください。[タスクの並列化](../task-parallelism-concurrency-runtime.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`task_group`

## <a name="requirements"></a>必要条件

**ヘッダー:** ppl.h

**名前空間:** concurrency

##  <a name="cancel"></a> キャンセル

このタスク グループをルートとする作業のサブツリーの取り消しを試行する最善の努力は、します。 タスク グループでスケジュールのすべてのタスクはキャンセル推移的に可能な場合。

```
void cancel();
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。[キャンセル](../cancellation-in-the-ppl.md)します。

##  <a name="is_canceling"></a> is_canceling

かどうか、タスク グループは現在キャンセル中、呼び出し元に通知します。 これは必ずしもを`cancel`でメソッドが呼び出された、`task_group`オブジェクト (もちろんを返すには、このメソッドを修飾などが`true`)。 ケースがある可能性があります`task_group`オブジェクトはインラインで実行し、さらに、タスク グループを作業ツリーが取り消されました。 これらの場所などの場合、ランタイムがキャンセルは、このフローは前もって確認できます`task_group`オブジェクト、`true`も返されます。

```
bool is_canceling();
```

### <a name="return-value"></a>戻り値

かどうかを示す値、`task_group`オブジェクト取り消しである (または間もなくことが保証されます)。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。[キャンセル](../cancellation-in-the-ppl.md)します。

##  <a name="run"></a> 実行

タスクをスケジュール、`task_group`オブジェクト。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run`の有効期間を管理するため、呼び出し元は、`task_handle`オブジェクト。 バージョンのパラメーターは、可能性のあるランタイム内でヒープ割り当て関数のオブジェクトへの参照を受け取るメソッドへの参照を受け取るバージョンを使用してより適切に機能しないの実行、`task_handle`オブジェクト。 パラメーターを受け取るバージョン`_Placement`タスクがそのパラメーターで指定された場所を実行して重きをさせます。

```
template<
   typename _Function
>
void run(
   const _Function& _Func
);

template<
   typename _Function
>
void run(
   const _Function& _Func,
   location& _Placement
);

template<
   typename _Function
>
void run(
   task_handle<_Function>& _Task_handle
);

template<
   typename _Function
>
void run(
   task_handle<_Function>& _Task_handle,
   location& _Placement
);
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
タスク ハンドルの本文を実行するときに呼び出される関数オブジェクトの型。

*_Func*<br/>
タスクの本体を呼び出すために呼び出される関数。 これは、ラムダ式またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクト`void operator()()`します。

*(_P)*<br/>
タスクがによって表される場所への参照、`_Func`パラメーターを実行する必要があります。

*_Task_handle*<br/>
スケジュールされている作業へのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任に注意してください。 ランタイムは引き続き想定されるまで、live、`wait`または`run_and_wait`このメソッドが呼び出された`task_group`オブジェクト。

### <a name="remarks"></a>Remarks

ランタイムは、後で、呼び出し元の関数が返された後に、これを実行する指定された処理関数をスケジュールします。 このメソッドを使用して、 [task_handle](task-handle-class.md)指定された処理関数のコピーを保持するオブジェクト。 そのため、このメソッドに渡すための関数オブジェクトで発生する状態の変更は、その関数のオブジェクトのコピーには表示されません。 また、作業関数が戻るまでポインターによって、または処理関数への参照によって渡された任意のオブジェクトの有効期間が有効であることを確認してください。

場合、 `task_group` destructs スタック アンワインド例外からの結果として、必要はありません、呼び出しが行われたいずれかにことを保証するために、`wait`または`run_and_wait`メソッド。 この場合、デストラクターが適切にキャンセルし、によって表されるタスクの待機、`_Task_handle`パラメーターを完了します。

メソッドはスロー、 [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md)タスクを処理する場合は例外によって指定された、`_Task_handle`パラメーターは既に使用してタスク グループ オブジェクトにスケジューリングされている、`run`メソッドがあったとありません介在するを呼び出すいずれかに、`wait`または`run_and_wait`そのタスク グループでのメソッド。

##  <a name="run_and_wait"></a> run_and_wait

呼び出し元のコンテキストでのインラインを実行するタスクをスケジュール、`task_group`オブジェクトの完全なキャンセルのサポート。 すべての作業になるまでにその後、関数が待機、`task_group`オブジェクトが完了したか取り消されました。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run_and_wait`の有効期間を管理するため、呼び出し元は、`task_handle`オブジェクト。

```
template<
   class _Function
>
task_group_status run_and_wait(
   task_handle<_Function>& _Task_handle
);

template<
   class _Function
>
task_group_status run_and_wait(
   const _Function& _Func
);
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
タスクの本体を実行するときに呼び出される関数オブジェクトの型。

*_Task_handle*<br/>
インライン呼び出し元のコンテキストで実行するタスクへのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任に注意してください。 ランタイムが本来はまで、引き続き、`run_and_wait`メソッドが実行を終了します。

*_Func*<br/>
作業の本体を呼び出すために呼び出される関数。 これは、ラムダ式またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクト`void operator()()`します。

### <a name="return-value"></a>戻り値

待機が満たされたかどうかを示す値、またはタスク グループは、明示的な取り消し操作をまたはいずれかのタスクからスローされる例外のためキャンセルされました。 詳細については、次を参照してください。 [task_group_status](concurrency-namespace-enums.md#task_group_status)します。

### <a name="remarks"></a>Remarks

その 1 つ以上の次のようにスケジュールされたタスクに注意してください`task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する可能性があります。

このスケジュールされたタスクの 1 つ以上の場合`task_group`オブジェクトが例外をスロー、ランタイムは、選択した場合のような例外が 1 つを選択しへの呼び出しから伝達されること、`run_and_wait`メソッド。

戻り時に、`run_and_wait`メソッドを`task_group`オブジェクトをランタイムに再利用することができます、クリーンな状態に、オブジェクトをリセットします。 場合も、`task_group`オブジェクトは取り消されました。

実行の例外的ではないパス、常に当てはまるか、このメソッドを呼び出す必要がある、または`wait`メソッドのデストラクターの前に、`task_group`を実行します。

##  <a name="ctor"></a> task_group

新しい `task_group` オブジェクトを構築します。

```
task_group();

task_group(
   cancellation_token _CancellationToken
);
```

### <a name="parameters"></a>パラメーター

*_CancellationToken*<br/>
このタスク グループに関連付けるキャンセル トークン。 タスク グループは、トークンが取り消されたときに取り消されます。

### <a name="remarks"></a>Remarks

キャンセル トークンを受け取るコンス トラクターを作成、`task_group`ですが、トークンに関連付けられたソースが取り消されたときにキャンセルされます。 別のトークンまたはトークンを設定せずに親グループからの暗黙的なキャンセルに参加している場合は、このタスク グループを分離も、明示的なキャンセル トークンを提供します。

##  <a name="dtor"></a> ~task_group

`task_group` オブジェクトを破棄します。 呼び出すか、予想される、`wait`または`run_and_wait`実行する前に、デストラクター、デストラクターがスタック アンワインドにより例外結果として実行しない限り、オブジェクトのメソッド。

```
~task_group();
```

### <a name="remarks"></a>Remarks

デストラクターは、通常の実行 (たとえば、stack ではない例外が原因のアンワインド) とも、結果として実行する場合、`wait`も`run_and_wait`メソッドが呼び出された、スローする可能性が、デストラクター、 [missing_wait](missing-wait-class.md)例外。

##  <a name="wait"></a> 待機

すべての作業になるまでの待機、`task_group`オブジェクトが完了したか取り消されました。

```
task_group_status wait();
```

### <a name="return-value"></a>戻り値

待機が満たされたかどうかを示す値、またはタスク グループは、明示的な取り消し操作をまたはいずれかのタスクからスローされる例外のためキャンセルされました。 詳細については、次を参照してください。 [task_group_status](concurrency-namespace-enums.md#task_group_status)します。

### <a name="remarks"></a>Remarks

その 1 つ以上の次のようにスケジュールされたタスクに注意してください`task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する可能性があります。

このスケジュールされたタスクの 1 つ以上の場合`task_group`オブジェクトが例外をスロー、ランタイムは、選択した場合のような例外が 1 つを選択しへの呼び出しから伝達されること、`wait`メソッド。

呼び出す`wait`上、`task_group`オブジェクトは、再利用することができます、クリーンな状態にリセットします。 場合も、`task_group`オブジェクトは取り消されました。

実行の例外的ではないパス、常に当てはまるか、このメソッドを呼び出す必要がある、または`run_and_wait`メソッドのデストラクターの前に、`task_group`を実行します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[structured_task_group クラス](structured-task-group-class.md)<br/>
[task_handle クラス](task-handle-class.md)
