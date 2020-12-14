---
description: '詳細情報: structured_task_group クラス'
title: structured_task_group クラス
ms.date: 11/04/2016
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
ms.openlocfilehash: c553f0d0b9b5abeb6e6cbdb12d1d9da5d048a6d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188457"
---
# <a name="structured_task_group-class"></a>structured_task_group クラス

`structured_task_group` クラスは、並列処理の高度に構造化されたコレクションを表します。 `structured_task_group` オブジェクトを使用して個々の並列タスクを `task_handle` のキューに配置し、それらのタスクが完了するまで待機するか、実行が完了する前にタスク グループを取り消すことができます。取り消すと、実行が開始されていないタスクはすべて中止されます。

## <a name="syntax"></a>構文

```cpp
class structured_task_group;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[structured_task_group](#ctor)|オーバーロードされます。 新しい `structured_task_group` オブジェクトを構築します。|
|[~ structured_task_group デストラクター](#dtor)|`structured_task_group` オブジェクトを破棄します。 `wait` `run_and_wait` 例外が原因でスタックアンワインドの結果としてデストラクターが実行されていない限り、デストラクターを実行する前に、オブジェクトに対してメソッドまたはメソッドのいずれかを呼び出す必要があります。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[cancel](#cancel)|では、このタスクグループをルートとする作業のサブツリーをキャンセルすることをお勧めします。 タスクグループにスケジュールされているすべてのタスクは、可能な場合は推移的に取り消されます。|
|[is_canceling](#is_canceling)|タスクグループが現在キャンセル中であるかどうかを呼び出し元に通知します。 これは、必ずしもオブジェクトでメソッドが呼び出されたことを示しているわけではありません (ただし、このメソッドによって返されることは `cancel` `structured_task_group` 確かです **`true`** )。 `structured_task_group`オブジェクトがインラインで実行されていて、作業ツリー内のタスクグループが取り消された場合もあります。 このような場合、ランタイムは、キャンセルがこのオブジェクトを通過する前に事前に判断でき `structured_task_group` **`true`** ますが、も返されます。|
|[実行](#run)|オーバーロードされます。 オブジェクトのタスクをスケジュール `structured_task_group` します。 呼び出し元は、パラメーターで渡されるオブジェクトの有効期間を管理し `task_handle` `_Task_handle` ます。 パラメーターを受け取るバージョンでは、 `_Placement` そのパラメーターによって指定された場所で実行されるようにタスクがバイアスされます。|
|[run_and_wait](#run_and_wait)|オーバーロードされます。 オブジェクトを使用して、呼び出し元のコンテキストでインラインで実行されるタスクをスケジュールし、 `structured_task_group` 完全なキャンセルをサポートします。 `task_handle`オブジェクトがのパラメーターとして渡された場合 `run_and_wait` 、呼び出し元はオブジェクトの有効期間を管理し `task_handle` ます。 次に、関数は、オブジェクトのすべての作業が完了するか取り消されるまで待機し `structured_task_group` ます。|
|[wait](#wait)|のすべての作業が完了するか、取り消されるまで待機 `structured_task_group` します。|

## <a name="remarks"></a>解説

パフォーマンスを向上させるために、オブジェクトの使用にはいくつかの重大な制限が設けられてい `structured_task_group` ます。

- 1つの `structured_task_group` オブジェクトを複数のスレッドで使用することはできません。 オブジェクトのすべての操作 `structured_task_group` は、オブジェクトを作成したスレッドによって実行される必要があります。 この規則の2つの例外は、メンバー関数 `cancel` と `is_canceling` です。 このオブジェクトは、タスクがキャンセル操作のいずれかを使用している場合を除き、ラムダ式のキャプチャリストに含まれておらず、タスク内で使用することができます。

- オブジェクトに対してスケジュール `structured_task_group` されているすべてのタスクは、 `task_handle` の有効期間を明示的に管理する必要があるオブジェクトを使用してスケジュールされます。

- 複数のグループは、完全に入れ子になった順序でのみ使用できます。 2つの `structured_task_group` オブジェクトが宣言されている場合は、宣言されている2番目のオブジェクト (内側のオブジェクト) が、 `cancel` `is_canceling` 最初のメソッド (外側のオブジェクト) で呼び出されるか、またはが呼び出される前に破棄する必要があります。 この条件は、 `structured_task_group` 同じまたは機能的に入れ子になったスコープ内で複数のオブジェクトを宣言する場合と、 `structured_task_group` メソッドまたはメソッドを使用してをキューに配置したタスクの場合の両方に当てはまり `run` `run_and_wait` ます。

- 一般クラスとは異なり `task_group` 、クラスのすべての状態 `structured_task_group` は final です。 グループに対してタスクをキューに入れて完了を待機した後、同じグループを再度使用することはできません。

詳細については、「 [タスクの並列](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)化」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`structured_task_group`

## <a name="requirements"></a>要件

**ヘッダー:** ppl

**名前空間:** concurrency

## <a name="cancel"></a><a name="cancel"></a> キャンセル

では、このタスクグループをルートとする作業のサブツリーをキャンセルすることをお勧めします。 タスクグループにスケジュールされているすべてのタスクは、可能な場合は推移的に取り消されます。

```cpp
void cancel();
```

### <a name="remarks"></a>解説

詳細については、「 [キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)」を参照してください。

## <a name="is_canceling"></a><a name="is_canceling"></a> is_canceling

タスクグループが現在キャンセル中であるかどうかを呼び出し元に通知します。 これは、必ずしもオブジェクトでメソッドが呼び出されたことを示しているわけではありません (ただし、このメソッドによって返されることは `cancel` `structured_task_group` 確かです **`true`** )。 `structured_task_group`オブジェクトがインラインで実行されていて、作業ツリー内のタスクグループが取り消された場合もあります。 このような場合、ランタイムは、キャンセルがこのオブジェクトを通過する前に事前に判断でき `structured_task_group` **`true`** ますが、も返されます。

```cpp
bool is_canceling();
```

### <a name="return-value"></a>戻り値

オブジェクトがキャンセルの途中であるかどうかを示す値 `structured_task_group` (または、間もなく保証されることが保証されます)。

### <a name="remarks"></a>解説

詳細については、「 [キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)」を参照してください。

## <a name="run"></a><a name="run"></a> 実行

オブジェクトのタスクをスケジュール `structured_task_group` します。 呼び出し元は、パラメーターで渡されるオブジェクトの有効期間を管理し `task_handle` `_Task_handle` ます。 パラメーターを受け取るバージョンでは、 `_Placement` そのパラメーターによって指定された場所で実行されるようにタスクがバイアスされます。

```cpp
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
タスクハンドルの本体を実行するために呼び出される関数オブジェクトの型。

*_Task_handle*<br/>
スケジュールされている作業へのハンドル。 呼び出し元は、このオブジェクトの有効期間を担当していることに注意してください。 ランタイムは、 `wait` `run_and_wait` このオブジェクトに対してメソッドまたはメソッドが呼び出されるまで、引き続き有効であると想定し `structured_task_group` ます。

*_Placement*<br/>
パラメーターによって表されるタスクが実行される場所への参照 `_Task_handle` 。

### <a name="remarks"></a>解説

ランタイムは、このメソッドに渡す作業関数のコピーを作成します。 このメソッドに渡す関数オブジェクトで発生した状態の変更は、その関数オブジェクトのコピーには表示されません。

`structured_task_group`例外からのスタックアンワインドの結果として destructs が発生した場合、 `wait` メソッドまたはメソッドのいずれかに対して呼び出しが行われたことを保証する必要はありません `run_and_wait` 。 この場合、デストラクターは適切にキャンセルされ、パラメーターによって表されるタスクが完了するまで待機し `_Task_handle` ます。

は、 [](invalid-multiple-scheduling-class.md)パラメーターによって指定されたタスクハンドルがメソッドを使用して `_Task_handle` タスクグループオブジェクトに既にスケジュールされて `run` おり、 `wait` `run_and_wait` そのタスクグループに対してメソッドまたはメソッドの呼び出しが介在していない場合に、invalid_multiple_scheduling 例外をスローします。

## <a name="run_and_wait"></a><a name="run_and_wait"></a> run_and_wait

オブジェクトを使用して、呼び出し元のコンテキストでインラインで実行されるタスクをスケジュールし、 `structured_task_group` 完全なキャンセルをサポートします。 `task_handle`オブジェクトがのパラメーターとして渡された場合 `run_and_wait` 、呼び出し元はオブジェクトの有効期間を管理し `task_handle` ます。 次に、関数は、オブジェクトのすべての作業が完了するか取り消されるまで待機し `structured_task_group` ます。

```cpp
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```

### <a name="parameters"></a>パラメーター

*_Function*<br/>
タスクを実行するために呼び出される関数オブジェクトの型。

*_Task_handle*<br/>
呼び出し元のコンテキストでインラインで実行されるタスクへのハンドル。 呼び出し元は、このオブジェクトの有効期間を担当していることに注意してください。 ランタイムは、メソッドが実行を終了するまで、引き続き有効であると想定し `run_and_wait` ます。

*_Func*<br/>
作業の本体を呼び出すために呼び出される関数。 これは、シグネチャを持つ関数呼び出し演算子のバージョンをサポートするラムダまたはその他のオブジェクトである可能性があり `void operator()()` ます。

### <a name="return-value"></a>戻り値

明示的な取り消し操作、またはそのタスクの1つからスローされた例外が原因で、待機が満たされたか、タスクグループが取り消されたかを示す値。 詳細については、「」を参照してください [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>解説

このオブジェクトに対してスケジュールされている1つ以上のタスク `structured_task_group` が、呼び出し元のコンテキストでインラインで実行される可能性があることに注意してください。

このオブジェクトに対してスケジュールされている1つ以上のタスクが例外をスローした場合、ランタイムはその例外を選択して、 `structured_task_group` メソッドの呼び出しの外に伝達し `run_and_wait` ます。

この関数がを返す `structured_task_group` と、オブジェクトは最終的な状態と見なされるため、使用しないでください。 メソッドから制御が戻った後の使用率によって、 `run_and_wait` 未定義の動作が発生することに注意してください。

実行の例外的なパスでは、 `wait` のデストラクターが実行される前に、このメソッドまたはメソッドのいずれかを呼び出す必要があり `structured_task_group` ます。

## <a name="structured_task_group"></a><a name="ctor"></a> structured_task_group

新しい `structured_task_group` オブジェクトを構築します。

```cpp
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```

### <a name="parameters"></a>パラメーター

*_CancellationToken*<br/>
この構造化タスクグループに関連付けるキャンセルトークン。 トークンが取り消されると、構造化タスクグループは取り消されます。

### <a name="remarks"></a>解説

キャンセルトークンを受け取るコンストラクターは、 `structured_task_group` トークンに関連付けられているソースが取り消されたときにキャンセルされるを作成します。 また、明示的なキャンセルトークンを指定すると、この構造化タスクグループは、別のトークンまたはトークンを持たない親グループからの暗黙的な取り消しに参加しないように分離されます。

## <a name="structured_task_group"></a><a name="dtor"></a> ~ structured_task_group

`structured_task_group` オブジェクトを破棄します。 `wait` `run_and_wait` 例外が原因でスタックアンワインドの結果としてデストラクターが実行されていない限り、デストラクターを実行する前に、オブジェクトに対してメソッドまたはメソッドのいずれかを呼び出す必要があります。

```cpp
~structured_task_group();
```

### <a name="remarks"></a>解説

デストラクターが通常の実行の結果として実行された場合 (たとえば、例外が原因でスタックアンワインドが発生していない場合)、 `wait` `run_and_wait` メソッドもメソッドも呼び出されていないと、デストラクターが [missing_wait](missing-wait-class.md) 例外をスローする可能性があります。

## <a name="wait"></a><a name="wait"></a> 待機

のすべての作業が完了するか、取り消されるまで待機 `structured_task_group` します。

```cpp
task_group_status wait();
```

### <a name="return-value"></a>戻り値

明示的な取り消し操作、またはそのタスクの1つからスローされた例外が原因で、待機が満たされたか、タスクグループが取り消されたかを示す値。 詳細については、「」を参照してください [task_group_status](concurrency-namespace-enums.md)

### <a name="remarks"></a>解説

このオブジェクトに対してスケジュールされている1つ以上のタスク `structured_task_group` が、呼び出し元のコンテキストでインラインで実行される可能性があることに注意してください。

このオブジェクトに対してスケジュールされている1つ以上のタスクが例外をスローした場合、ランタイムはその例外を選択して、 `structured_task_group` メソッドの呼び出しの外に伝達し `wait` ます。

この関数がを返す `structured_task_group` と、オブジェクトは最終的な状態と見なされるため、使用しないでください。 メソッドから制御が戻った後の使用率によって、 `wait` 未定義の動作が発生することに注意してください。

実行の例外的なパスでは、 `run_and_wait` のデストラクターが実行される前に、このメソッドまたはメソッドのいずれかを呼び出す必要があり `structured_task_group` ます。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[task_group クラス](task-group-class.md)<br/>
[task_handle クラス](task-handle-class.md)
