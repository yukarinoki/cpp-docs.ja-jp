---
title: structured_task_group クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
dev_langs:
- C++
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4aa6df9afddc43980818439ee2c7bbd29ca2f848
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446076"
---
# <a name="structuredtaskgroup-class"></a>structured_task_group クラス

`structured_task_group` クラスは、並列処理の高度に構造化されたコレクションを表します。 `structured_task_group` オブジェクトを使用して個々の並列タスクを `task_handle` のキューに配置し、それらのタスクが完了するまで待機するか、実行が完了する前にタスク グループを取り消すことができます。取り消すと、実行が開始されていないタスクはすべて中止されます。

## <a name="syntax"></a>構文

```
class structured_task_group;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[structured_task_group](#ctor)|オーバーロードされます。 新しい `structured_task_group` オブジェクトを構築します。|
|[~ structured_task_group デストラクター](#dtor)|`structured_task_group` オブジェクトを破棄します。 いずれかを呼び出さない予想される、`wait`または`run_and_wait`デストラクターの実行前にオブジェクトのメソッド、デストラクターが実行されていない場合の結果としてスタック アンワインド例外が原因です。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[キャンセル](#cancel)|このタスク グループをルートとする作業のサブツリーの取り消しを試行する最善の努力は、します。 タスク グループでスケジュールのすべてのタスクはキャンセル推移的に可能な場合。|
|[is_canceling](#is_canceling)|かどうか、タスク グループは現在キャンセル中、呼び出し元に通知します。 これは必ずしもを`cancel`でメソッドが呼び出された、`structured_task_group`オブジェクト (もちろんを返すには、このメソッドを修飾などが`true`)。 ケースがある可能性があります`structured_task_group`オブジェクトはインラインで実行し、さらに、タスク グループを作業ツリーが取り消されました。 これらの場所などの場合、ランタイムがキャンセルは、このフローは前もって確認できます`structured_task_group`オブジェクト、`true`も返されます。|
|[run](#run)|オーバーロードされます。 タスクをスケジュール、`structured_task_group`オブジェクト。 呼び出し元の有効期間の管理、`task_handle`で渡されるオブジェクト、`_Task_handle`パラメーター。 パラメーターを受け取るバージョン`_Placement`タスクがそのパラメーターで指定された場所を実行して重きをさせます。|
|[run_and_wait](#run_and_wait)|オーバーロードされます。 呼び出し元のコンテキストでのインラインを実行するタスクをスケジュール、`structured_task_group`オブジェクトの完全なキャンセルのサポート。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run_and_wait`の有効期間を管理するため、呼び出し元は、`task_handle`オブジェクト。 すべての作業になるまでにその後、関数が待機、`structured_task_group`オブジェクトが完了したか取り消されました。|
|[wait](#wait)|すべての作業になるまでの待機、`structured_task_group`が完了またはキャンセルします。|

## <a name="remarks"></a>Remarks

使用状況の重大な制限がいくつか、`structured_task_group`オブジェクトのパフォーマンスを得るためには。

- 1 つ`structured_task_group`オブジェクトは、複数のスレッドでは使用できません。 すべての操作を`structured_task_group`オブジェクトは、オブジェクトを作成したスレッドで実行する必要があります。 このルールは、2 つの例外は、メンバー関数`cancel`と`is_canceling`します。 オブジェクトは、ラムダ式のキャプチャ リストにできない可能性があり、タスクがキャンセル操作のいずれかを使用していない場合、タスク内で使用します。

- スケジュールされているすべてのタスクを`structured_task_group`オブジェクトを使用してスケジュール`task_handle`オブジェクトの有効期間を明示的に管理する必要があります。

- 複数のグループは、絶対に入れ子になった順序でのみ使用可能性があります。 2 つ`structured_task_group`オブジェクトが宣言されている、(内部の 1 つ) が宣言されている 2 つ目を除く任意のメソッドの前に破棄する必要があります`cancel`または`is_canceling`が 1 つ目で呼び出されます (外側のいずれか)。 複数を宣言するだけの場合の両方でこの条件に当てはまる`structured_task_group`のキューに登録されたタスクの場合と同様に、同じまたは機能的に入れ子になったスコープ内のオブジェクト、`structured_task_group`を使用して、`run`または`run_and_wait`メソッド。

- 一般的なとは異なり`task_group`クラス内のすべての状態、`structured_task_group`クラスは元に戻せません。 グループにタスクをキューに登録し、その完了を待機した後、同じグループをもう一度使用することはできません。

詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`structured_task_group`

## <a name="requirements"></a>要件

**ヘッダー:** ppl.h

**名前空間:** concurrency

##  <a name="cancel"></a> キャンセル

このタスク グループをルートとする作業のサブツリーの取り消しを試行する最善の努力は、します。 タスク グループでスケジュールのすべてのタスクはキャンセル推移的に可能な場合。

```
void cancel();
```

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。[キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)します。

##  <a name="is_canceling"></a> is_canceling

かどうか、タスク グループは現在キャンセル中、呼び出し元に通知します。 これは必ずしもを`cancel`でメソッドが呼び出された、`structured_task_group`オブジェクト (もちろんを返すには、このメソッドを修飾などが`true`)。 ケースがある可能性があります`structured_task_group`オブジェクトはインラインで実行し、さらに、タスク グループを作業ツリーが取り消されました。 これらの場所などの場合、ランタイムがキャンセルは、このフローは前もって確認できます`structured_task_group`オブジェクト、`true`も返されます。

```
bool is_canceling();
```

### <a name="return-value"></a>戻り値

かどうかを示す値、`structured_task_group`オブジェクト取り消しである (または間もなくことが保証されます)。

### <a name="remarks"></a>Remarks

詳細については、次を参照してください。[キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)します。

##  <a name="run"></a> 実行

タスクをスケジュール、`structured_task_group`オブジェクト。 呼び出し元の有効期間の管理、`task_handle`で渡されるオブジェクト、`_Task_handle`パラメーター。 パラメーターを受け取るバージョン`_Placement`タスクがそのパラメーターで指定された場所を実行して重きをさせます。

```
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
タスク ハンドルの本文を実行するときに呼び出される関数オブジェクトの型。

*_Task_handle*<br/>
スケジュールされている作業へのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任に注意してください。 ランタイムは引き続き想定されるまで、live、`wait`または`run_and_wait`このメソッドが呼び出された`structured_task_group`オブジェクト。

*(_P)*<br/>
タスクがによって表される場所への参照、`_Task_handle`パラメーターを実行する必要があります。

### <a name="remarks"></a>Remarks

ランタイムは、このメソッドに渡す処理関数のコピーを作成します。 このメソッドに渡すための関数オブジェクトで発生する状態の変更は、その関数のオブジェクトのコピーには表示されません。

場合、 `structured_task_group` destructs スタック アンワインド例外からの結果として、必要はありません、呼び出しが行われたいずれかにことを保証するために、`wait`または`run_and_wait`メソッド。 この場合、デストラクターが適切にキャンセルし、によって表されるタスクの待機、`_Task_handle`パラメーターを完了します。

スローされます、 [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md)タスクを処理する場合は例外によって指定された、`_Task_handle`パラメーターは既に使用してタスク グループ オブジェクトにスケジューリングされている、`run`メソッドがなかった中間の呼び出しといずれか、`wait`または`run_and_wait`そのタスク グループでのメソッド。

##  <a name="run_and_wait"></a> run_and_wait

呼び出し元のコンテキストでのインラインを実行するタスクをスケジュール、`structured_task_group`オブジェクトの完全なキャンセルのサポート。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run_and_wait`の有効期間を管理するため、呼び出し元は、`task_handle`オブジェクト。 すべての作業になるまでにその後、関数が待機、`structured_task_group`オブジェクトが完了したか取り消されました。

```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
タスクを実行するときに呼び出される関数オブジェクトの型。

*_Task_handle*<br/>
インライン呼び出し元のコンテキストで実行するタスクへのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任に注意してください。 ランタイムが本来はまで、引き続き、`run_and_wait`メソッドが実行を終了します。

*_Func*<br/>
作業の本体を呼び出すために呼び出される関数。 これは、ラムダまたはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクト`void operator()()`します。

### <a name="return-value"></a>戻り値

待機が満たされたかどうかを示す値、またはタスク グループは、明示的な取り消し操作をまたはいずれかのタスクからスローされる例外のためキャンセルされました。 詳細については、次を参照してください[task_group_status。](concurrency-namespace-enums.md)

### <a name="remarks"></a>Remarks

その 1 つ以上の次のようにスケジュールされたタスクに注意してください`structured_task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する可能性があります。

このスケジュールされたタスクの 1 つ以上の場合`structured_task_group`オブジェクトが例外をスロー、ランタイムは、選択した場合のような例外が 1 つを選択しへの呼び出しから伝達されること、`run_and_wait`メソッド。

この関数を返した後、`structured_task_group`オブジェクトが最終的な状態と見なされは使用できません。 その後の使用率に注意してください、`run_and_wait`メソッドを返します未定義の動作になります。

実行の例外的ではないパス、常に当てはまるか、このメソッドを呼び出す必要がある、または`wait`メソッドのデストラクターの前に、`structured_task_group`を実行します。

##  <a name="ctor"></a> structured_task_group

新しい `structured_task_group` オブジェクトを構築します。

```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```

### <a name="parameters"></a>パラメーター

*_CancellationToken*<br/>
この構造化タスク グループに関連付けるキャンセル トークン。 構造化タスク グループは、トークンが取り消されたときに取り消されます。

### <a name="remarks"></a>Remarks

キャンセル トークンを受け取るコンス トラクターを作成、`structured_task_group`ですが、トークンに関連付けられたソースが取り消されたときにキャンセルされます。 別のトークンまたはトークンを設定せずに親グループからの暗黙的なキャンセルに参加している場合は、この構造化タスク グループを分離も、明示的なキャンセル トークンを提供します。

##  <a name="dtor"></a> ~structured_task_group

`structured_task_group` オブジェクトを破棄します。 いずれかを呼び出さない予想される、`wait`または`run_and_wait`デストラクターの実行前にオブジェクトのメソッド、デストラクターが実行されていない場合の結果としてスタック アンワインド例外が原因です。

```
~structured_task_group();
```

### <a name="remarks"></a>Remarks

デストラクターは、通常の実行 (たとえば、stack ではない例外が原因のアンワインド) とも、結果として実行する場合、`wait`も`run_and_wait`メソッドが呼び出された、スローする可能性が、デストラクター、 [missing_wait](missing-wait-class.md)例外。

##  <a name="wait"></a> 待機

すべての作業になるまでの待機、`structured_task_group`が完了またはキャンセルします。

```
task_group_status wait();
```

### <a name="return-value"></a>戻り値

待機が満たされたかどうかを示す値、またはタスク グループは、明示的な取り消し操作をまたはいずれかのタスクからスローされる例外のためキャンセルされました。 詳細については、次を参照してください[task_group_status。](concurrency-namespace-enums.md)

### <a name="remarks"></a>Remarks

その 1 つ以上の次のようにスケジュールされたタスクに注意してください`structured_task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する可能性があります。

このスケジュールされたタスクの 1 つ以上の場合`structured_task_group`オブジェクトが例外をスロー、ランタイムは、選択した場合のような例外が 1 つを選択しへの呼び出しから伝達されること、`wait`メソッド。

この関数を返した後、`structured_task_group`オブジェクトが最終的な状態と見なされは使用できません。 その後の使用率に注意してください、`wait`メソッドを返します未定義の動作になります。

実行の例外的ではないパス、常に当てはまるか、このメソッドを呼び出す必要がある、または`run_and_wait`メソッドのデストラクターの前に、`structured_task_group`を実行します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[task_group クラス](task-group-class.md)<br/>
[task_handle クラス](task-handle-class.md)
