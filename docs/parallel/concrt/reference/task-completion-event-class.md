---
title: task_completion_event クラス
ms.date: 11/04/2016
f1_keywords:
- task_completion_event
- PPLTASKS/concurrency::task_completion_event
- PPLTASKS/concurrency::task_completion_event::task_completion_event
- PPLTASKS/concurrency::task_completion_event::set
- PPLTASKS/concurrency::task_completion_event::set_exception
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
ms.openlocfilehash: 9d0ab271b20eb02c1dc4cb8e54cf2632eead4325
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212886"
---
# <a name="taskcompletionevent-class"></a>task_completion_event クラス

`task_completion_event` クラスを使用すると、条件が満たされるまで、または外部イベントに応答してタスクを開始するまで、タスクの実行を遅延できます。

## <a name="syntax"></a>構文

```
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```

#### <a name="parameters"></a>パラメーター

*_ResultType*<br/>
この `task_completion_event` クラスの結果の型。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[task_completion_event](#ctor)|`task_completion_event` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[set](#set)|オーバーロードされます。 タスクの完了イベントを設定します。|
|[set_exception](#set_exception)|オーバーロードされます。 このイベントに関連付けられているすべてのタスクに例外を反映します。|

## <a name="remarks"></a>Remarks

タスクを作成するシナリオで、将来のいずれかの時点でタスクが終了し、そのタスクの継続が実行されるようにスケジュールする必要がある場合、タスクの完了イベントから作成されるタスクを使用します。 `task_completion_event` には、作成するタスクと同じ型を含める必要があります。また、その型の値を使用し、タスクの完了イベントで set メソッドを呼び出すと、関連するタスクが完了し、その値が結果としてタスクの継続に渡されます。

タスクの完了イベントがシグナルを受け取らない場合、そのイベントから作成されたタスクは、イベントが破棄されるときに取り消されます。

`task_completion_event` は、スマート ポインターのように動作し、値渡しされる必要があります。

## <a name="inheritance-hierarchy"></a>継承階層

`task_completion_event`

## <a name="requirements"></a>必要条件

**ヘッダー:** ppltasks.h

**名前空間:** concurrency

##  <a name="set"></a> 設定

タスクの完了イベントを設定します。

```
bool set(_ResultType _Result) const ;

bool set() const ;
```

### <a name="parameters"></a>パラメーター

*_Result*<br/>
このイベントを設定する結果。

### <a name="return-value"></a>戻り値

メソッドを返します**true**イベントの設定に成功した場合。 返します**false**イベントは既に設定されている場合。

### <a name="remarks"></a>Remarks

`set` の複数呼び出しまたは同時呼び出しがある場合、最初の呼び出しだけが成功し、その結果 (結果が返される場合) はタスクの完了イベントに格納されます。 その他の set は無視され、メソッドは false を返します。 タスクの完了イベントを設定すると、そのイベントから作成されたすべてのタスクは直ちに完了します。また継続が存在する場合は、その継続がスケジュールされます。 タスクの完了オブジェクトを持つ、`_ResultType`以外**void**その継続に値を渡します。

##  <a name="set_exception"></a> set_exception

このイベントに関連付けられているすべてのタスクに例外を反映します。

```
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```

### <a name="parameters"></a>パラメーター

*_E*<br/>
例外の種類。

*_Except*<br/>
設定する例外。

*_ExceptionPtr*<br/>
例外のカーソルを設定します。

### <a name="return-value"></a>戻り値

##  <a name="ctor"></a> task_completion_event

`task_completion_event` オブジェクトを構築します。

```
task_completion_event();
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
