---
description: '詳細情報: task_group クラス'
title: task_group クラス
ms.date: 07/20/2018
f1_keywords:
- task_group
- PPL/concurrency::task_group
- PPL/concurrency::task_group::task_group
helpviewer_keywords:
- task_group class
ms.openlocfilehash: 8ac3fac0e1feadc2e6c609ee6a0c2946f5061bd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188242"
---
# <a name="task_group-class"></a>task_group クラス

`task_group` クラスは、待機または取り消しができる並列処理のコレクションを表します。

## <a name="syntax"></a>構文

```cpp
class task_group;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[task_group](#ctor)|オーバーロードされます。 新しい `task_group` オブジェクトを構築します。|
|[~ task_group デストラクター](#dtor)|`task_group` オブジェクトを破棄します。 デストラクター `wait` `run_and_wait` が例外によりスタックアンワインドの結果として実行されている場合を除き、デストラクターを実行する前に、オブジェクトに対してメソッドまたはメソッドのいずれかを呼び出す必要があります。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[cancel](#cancel)|では、このタスクグループをルートとする作業のサブツリーをキャンセルすることをお勧めします。 タスクグループにスケジュールされているすべてのタスクは、可能な場合は推移的に取り消されます。|
|[is_canceling](#is_canceling)|タスクグループが現在キャンセル中であるかどうかを呼び出し元に通知します。 これは、必ずしもオブジェクトでメソッドが呼び出されたことを示しているわけではありません (ただし、このメソッドによって返されることは `cancel` `task_group` 確かです **`true`** )。 `task_group`オブジェクトがインラインで実行されていて、作業ツリー内のタスクグループが取り消された場合もあります。 このような場合、ランタイムは、キャンセルがこのオブジェクトを通過する前に事前に判断でき `task_group` **`true`** ますが、も返されます。|
|[実行](#run)|オーバーロードされます。 オブジェクトのタスクをスケジュール `task_group` します。 `task_handle`オブジェクトがのパラメーターとして渡された場合 `run` 、呼び出し元はオブジェクトの有効期間を管理し `task_handle` ます。 パラメーターとして関数オブジェクトへの参照を受け取るメソッドのバージョンは、ランタイム内でのヒープ割り当てを伴い、オブジェクトへの参照を受け取るバージョンを使用する場合よりもパフォーマンスが低下する可能性があり `task_handle` ます。 パラメーターを受け取るバージョンでは、 `_Placement` そのパラメーターによって指定された位置でタスクの実行がバイアスされます。|
|[run_and_wait](#run_and_wait)|オーバーロードされます。 オブジェクトを使用して、呼び出し元のコンテキストでインラインで実行されるタスクをスケジュールし、 `task_group` 完全なキャンセルをサポートします。 次に、関数は、オブジェクトのすべての作業が完了するか取り消されるまで待機し `task_group` ます。 `task_handle`オブジェクトがのパラメーターとして渡された場合 `run_and_wait` 、呼び出し元はオブジェクトの有効期間を管理し `task_handle` ます。|
|[wait](#wait)|オブジェクトのすべての作業が完了するか、キャンセルされるまで待機 `task_group` します。|

## <a name="remarks"></a>解説

非常に制限の厳しいクラスとは異なり、 `structured_task_group` `task_group` クラスはより一般的なコンストラクトです。 [Structured_task_group](structured-task-group-class.md)で説明されている制限事項はありません。 `task_group` オブジェクトはスレッド間で安全に使用でき、自由形式の方法で利用できます。 コンストラクトの欠点は、 `task_group` `structured_task_group` 少量の作業を実行するタスクのコンストラクトに加えて、実行されない可能性があることです。

詳細については、「 [タスクの並列](../task-parallelism-concurrency-runtime.md)化」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`task_group`

## <a name="requirements"></a>要件

**ヘッダー:** ppl

**名前空間:** concurrency

## <a name="cancel"></a><a name="cancel"></a> キャンセル

では、このタスクグループをルートとする作業のサブツリーをキャンセルすることをお勧めします。 タスクグループにスケジュールされているすべてのタスクは、可能な場合は推移的に取り消されます。

```cpp
void cancel();
```

### <a name="remarks"></a>解説

詳細については、「 [キャンセル](../cancellation-in-the-ppl.md)」を参照してください。

## <a name="is_canceling"></a><a name="is_canceling"></a> is_canceling

タスクグループが現在キャンセル中であるかどうかを呼び出し元に通知します。 これは、必ずしもオブジェクトでメソッドが呼び出されたことを示しているわけではありません (ただし、このメソッドによって返されることは `cancel` `task_group` 確かです **`true`** )。 `task_group`オブジェクトがインラインで実行されていて、作業ツリー内のタスクグループが取り消された場合もあります。 このような場合、ランタイムは、キャンセルがこのオブジェクトを通過する前に事前に判断でき `task_group` **`true`** ますが、も返されます。

```cpp
bool is_canceling();
```

### <a name="return-value"></a>戻り値

オブジェクトがキャンセルの途中であるかどうかを示す値 `task_group` (または、間もなく保証されることが保証されます)。

### <a name="remarks"></a>解説

詳細については、「 [キャンセル](../cancellation-in-the-ppl.md)」を参照してください。

## <a name="run"></a><a name="run"></a> 実行

オブジェクトのタスクをスケジュール `task_group` します。 `task_handle`オブジェクトがのパラメーターとして渡された場合 `run` 、呼び出し元はオブジェクトの有効期間を管理し `task_handle` ます。 パラメーターとして関数オブジェクトへの参照を受け取るメソッドのバージョンは、ランタイム内でのヒープ割り当てを伴い、オブジェクトへの参照を受け取るバージョンを使用する場合よりもパフォーマンスが低下する可能性があり `task_handle` ます。 パラメーターを受け取るバージョンでは、 `_Placement` そのパラメーターによって指定された位置でタスクの実行がバイアスされます。

```cpp
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
タスクハンドルの本体を実行するために呼び出される関数オブジェクトの型。

*_Func*<br/>
タスクの本体を呼び出すために呼び出される関数。 これは、ラムダ式、またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクトである可能性があり `void operator()()` ます。

*_Placement*<br/>
パラメーターによって表されるタスクが実行される場所への参照 `_Func` 。

*_Task_handle*<br/>
スケジュールされている作業へのハンドル。 呼び出し元は、このオブジェクトの有効期間を担当していることに注意してください。 ランタイムは、 `wait` `run_and_wait` このオブジェクトに対してメソッドまたはメソッドが呼び出されるまで、引き続き有効であると想定し `task_group` ます。

### <a name="remarks"></a>解説

ランタイムは、指定された作業関数を後で実行するようにスケジュールを設定します。これは、呼び出し元の関数から制御が戻った後でも実行できます。 このメソッドは、 [task_handle](task-handle-class.md) オブジェクトを使用して、指定された作業関数のコピーを保持します。 このため、このメソッドに渡す関数オブジェクトで発生した状態の変更は、その関数オブジェクトのコピーには表示されません。 また、ポインターによって渡されるオブジェクトまたは work 関数への参照によって渡されるオブジェクトの有効期間は、処理関数が返されるまで有効なままにしておいてください。

`task_group`例外からのスタックアンワインドの結果として destructs が発生した場合、 `wait` メソッドまたはメソッドのいずれかに対して呼び出しが行われたことを保証する必要はありません `run_and_wait` 。 この場合、デストラクターは適切にキャンセルされ、パラメーターによって表されるタスクが完了するまで待機し `_Task_handle` ます。

パラメーターによって[](invalid-multiple-scheduling-class.md)指定されたタスクハンドルがメソッドを `_Task_handle` 使用してタスクグループオブジェクトに既にスケジュールされていて、 `run` `wait` `run_and_wait` そのタスクグループに対してメソッドまたはメソッドの呼び出しが介在していない場合、メソッドは invalid_multiple_scheduling 例外をスローします。

## <a name="run_and_wait"></a><a name="run_and_wait"></a> run_and_wait

オブジェクトを使用して、呼び出し元のコンテキストでインラインで実行されるタスクをスケジュールし、 `task_group` 完全なキャンセルをサポートします。 次に、関数は、オブジェクトのすべての作業が完了するか取り消されるまで待機し `task_group` ます。 `task_handle`オブジェクトがのパラメーターとして渡された場合 `run_and_wait` 、呼び出し元はオブジェクトの有効期間を管理し `task_handle` ます。

```cpp
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
タスクの本体を実行するために呼び出される関数オブジェクトの型。

*_Task_handle*<br/>
呼び出し元のコンテキストでインラインで実行されるタスクへのハンドル。 呼び出し元は、このオブジェクトの有効期間を担当していることに注意してください。 ランタイムは、メソッドが実行を終了するまで、引き続き有効であると想定し `run_and_wait` ます。

*_Func*<br/>
作業の本体を呼び出すために呼び出される関数。 これは、ラムダ式、またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクトである可能性があり `void operator()()` ます。

### <a name="return-value"></a>戻り値

明示的な取り消し操作、またはそのタスクの1つからスローされた例外が原因で、待機が満たされたか、タスクグループが取り消されたかを示す値。 詳細については、「 [task_group_status](concurrency-namespace-enums.md#task_group_status)」を参照してください。

### <a name="remarks"></a>解説

このオブジェクトに対してスケジュールされている1つ以上のタスク `task_group` が、呼び出し元のコンテキストでインラインで実行される可能性があることに注意してください。

このオブジェクトに対してスケジュールされている1つ以上のタスクが例外をスローした場合、ランタイムはその例外を選択して、 `task_group` メソッドの呼び出しの外に伝達し `run_and_wait` ます。

オブジェクトのメソッドから戻ると `run_and_wait` `task_group` 、ランタイムはオブジェクトを再利用できるクリーンな状態にリセットします。 これには、オブジェクトが取り消された場合も含まれ `task_group` ます。

実行の例外的なパスでは、 `wait` のデストラクターが実行される前に、このメソッドまたはメソッドのいずれかを呼び出す必要があり `task_group` ます。

## <a name="task_group"></a><a name="ctor"></a> task_group

新しい `task_group` オブジェクトを構築します。

```cpp
task_group();

task_group(
   cancellation_token _CancellationToken
);
```

### <a name="parameters"></a>パラメーター

*_CancellationToken*<br/>
このタスクグループに関連付けるキャンセルトークン。 トークンが取り消されると、タスクグループは取り消されます。

### <a name="remarks"></a>解説

キャンセルトークンを受け取るコンストラクターは、 `task_group` トークンに関連付けられているソースが取り消されたときにキャンセルされるを作成します。 また、明示的なキャンセルトークンを指定すると、このタスクグループは、別のトークンまたはトークンを持たない親グループからの暗黙的な取り消しに参加しないように分離されます。

## <a name="task_group"></a><a name="dtor"></a> ~ task_group

`task_group` オブジェクトを破棄します。 デストラクター `wait` `run_and_wait` が例外によりスタックアンワインドの結果として実行されている場合を除き、デストラクターを実行する前に、オブジェクトに対してメソッドまたはメソッドのいずれかを呼び出す必要があります。

```cpp
~task_group();
```

### <a name="remarks"></a>解説

デストラクターが通常の実行の結果として実行された場合 (たとえば、例外が原因でスタックアンワインドが発生していない場合)、 `wait` `run_and_wait` メソッドもメソッドも呼び出されていないと、デストラクターが [missing_wait](missing-wait-class.md) 例外をスローする可能性があります。

## <a name="wait"></a><a name="wait"></a> 待機

オブジェクトのすべての作業が完了するか、キャンセルされるまで待機 `task_group` します。

```cpp
task_group_status wait();
```

### <a name="return-value"></a>戻り値

明示的な取り消し操作、またはそのタスクの1つからスローされた例外が原因で、待機が満たされたか、タスクグループが取り消されたかを示す値。 詳細については、「 [task_group_status](concurrency-namespace-enums.md#task_group_status)」を参照してください。

### <a name="remarks"></a>解説

このオブジェクトに対してスケジュールされている1つ以上のタスク `task_group` が、呼び出し元のコンテキストでインラインで実行される可能性があることに注意してください。

このオブジェクトに対してスケジュールされている1つ以上のタスクが例外をスローした場合、ランタイムはその例外を選択して、 `task_group` メソッドの呼び出しの外に伝達し `wait` ます。

オブジェクトでを呼び出すと、 `wait` `task_group` 再利用できるクリーンな状態にリセットされます。 これには、オブジェクトが取り消された場合も含まれ `task_group` ます。

実行の例外的なパスでは、 `run_and_wait` のデストラクターが実行される前に、このメソッドまたはメソッドのいずれかを呼び出す必要があり `task_group` ます。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[structured_task_group クラス](structured-task-group-class.md)<br/>
[task_handle クラス](task-handle-class.md)
