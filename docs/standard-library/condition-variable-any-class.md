---
title: condition_variable_any クラス
ms.date: 11/04/2016
f1_keywords:
- condition_variable/std::condition_variable_any
- condition_variable/std::condition_variable_any::condition_variable_any
- condition_variable/std::condition_variable_any::notify_all
- condition_variable/std::condition_variable_any::notify_one
- condition_variable/std::condition_variable_any::wait
- condition_variable/std::condition_variable_any::wait_for
- condition_variable/std::condition_variable_any::wait_until
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
helpviewer_keywords:
- std::condition_variable_any
- std::condition_variable_any::condition_variable_any
- std::condition_variable_any::notify_all
- std::condition_variable_any::notify_one
- std::condition_variable_any::wait
- std::condition_variable_any::wait_for
- std::condition_variable_any::wait_until
ms.openlocfilehash: c38c080b0a8dbd9d4b0b76496aa367fa55892f50
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598160"
---
# <a name="conditionvariableany-class"></a>condition_variable_any クラス

`condition_variable_any` 型を持つイベントを待機するには、クラス `mutex` を使用します。

## <a name="syntax"></a>構文

```cpp
class condition_variable_any;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[condition_variable_any](#condition_variable_any)|`condition_variable_any` オブジェクトを構築します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[notify_all](#notify_all)|`condition_variable_any` オブジェクトを待機しているすべてのスレッドのブロックを解除します。|
|[notify_one](#notify_one)|`condition_variable_any` オブジェクトを待機しているスレッドの 1 つのブロックを解除します。|
|[wait](#wait)|スレッドをブロックします。|
|[wait_for](#wait_for)|スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。|
|[wait_until](#wait_until)|スレッドをブロックし、スレッドがブロック解除される最大の時刻を設定します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<condition_variable >

**名前空間:** std

## <a name="condition_variable_any"></a>  condition_variable_any::condition_variable_any コンストラクター

`condition_variable_any` オブジェクトを構築します。

```cpp
condition_variable_any();
```

### <a name="remarks"></a>Remarks

十分なメモリが使用できない場合、コンストラクターは `not_enough_memory` エラー コードがある [system_error](../standard-library/system-error-class.md) オブジェクトをスローします。 他のリソースをいくつか使用できないためにオブジェクトが構築できない場合、コンストラクターは `system_error` エラー コードがある `resource_unavailable_try_again` オブジェクトをスローします。

## <a name="notify_all"></a>  condition_variable_any::notify_all

`condition_variable_any` オブジェクトを待機しているすべてのスレッドのブロックを解除します。

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a>  condition_variable_any::notify_one

`condition_variable_any` オブジェクトを待機しているスレッドの 1 つのブロックを解除します。

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a>  condition_variable_any::wait

スレッドをブロックします。

```cpp
template <class Lock>
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```

### <a name="parameters"></a>パラメーター

*Lck*<br/>
任意の型の `mutex` オブジェクト。

*Pred*<br/>
任意の式を返す**true**または**false**します。

### <a name="remarks"></a>Remarks

最初のメソッドは `condition_variable_any` オブジェクトが [notify_one](../standard-library/condition-variable-class.md#notify_one) または [notify_all](../standard-library/condition-variable-class.md#notify_all) への呼び出しによって通知されるまでブロックします。 また、擬似的に開始することもできます。

実際には、2 つ目のメソッドは次のコードを実行します。

```cpp
while (!Pred())
    wait(Lck);
```

## <a name="wait_for"></a>  condition_variable_any::wait_for

スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。

```cpp
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```

### <a name="parameters"></a>パラメーター

*Lck*<br/>
任意の型の `mutex` オブジェクト。

*Rel_time*<br/>
スレッドが開始するまでの時間の長さを指定する `chrono::duration` オブジェクト。

*Pred*<br/>
任意の式を返す**true**または**false**します。

### <a name="return-value"></a>戻り値

最初のメソッドを返します`cv_status::timeout`待機が終了したときに場合*Rel_time*が経過しました。 それ以外の場合、メソッドは `cv_status::no_timeout` を返します。

2 番目のメソッドの値を返します*Pred*します。

### <a name="remarks"></a>Remarks

最初のメソッドがブロックされるまで、`condition_variable_any`への呼び出しによってオブジェクトがシグナル状態[notify_one](../standard-library/condition-variable-class.md#notify_one)または[notify_all](../standard-library/condition-variable-class.md#notify_all)、または時間間隔まで*Rel_time*が経過しました。 また、擬似的に開始することもできます。

実際には、2 つ目のメソッドは次のコードを実行します。

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a>  condition_variable_any::wait_until

スレッドをブロックし、スレッドがブロック解除される最大の時刻を設定します。

```cpp
template <class Lock, class Clock, class Duration>
void wait_until(Lock& Lck, const chrono::time_point<Clock, Duration>& Abs_time);

template <class Lock, class Clock, class Duration, class Predicate>
void wait_until(
    Lock& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

template <class Lock>
void wait_until(Lock Lck, const xtime* Abs_time);

template <class Lock, class Predicate>
void wait_until(
    Lock Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>パラメーター

*Lck*<br/>
ミューテックス オブジェクト。

*Abs_time*<br/>
[chrono::time_point](../standard-library/time-point-class.md) オブジェクト。

*Pred*<br/>
任意の式を返す**true**または**false**します。

### <a name="return-value"></a>戻り値

返すメソッドを`cv_status`戻り値を入力`cv_status::timeout`待機が終了したときに場合*Abs_time*が経過するとします。 それ以外の場合、メソッドは `cv_status::no_timeout` を返します。

返すメソッドを`bool`の値を返す*Pred*します。

### <a name="remarks"></a>Remarks

最初のメソッドがブロックされるまで、`condition_variable`への呼び出しによってオブジェクトがシグナル状態[notify_one](../standard-library/condition-variable-class.md#notify_one)または[notify_all](../standard-library/condition-variable-class.md#notify_all)、まで、または*Abs_time*します。 また、擬似的に開始することもできます。

実際には、2 つ目のメソッドは次のコードを実行します。

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

3 つ目のメソッドと 4 つ目のメソッドは、`xtime` 型のオブジェクトへのポインターを使用して、`chrono::time_point` オブジェクトを置き換えます。 `xtime` オブジェクトは、シグナルを待機する時間の最大値を指定します。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[<condition_variable>](../standard-library/condition-variable.md)<br/>
