---
description: '詳細情報: condition_variable_any クラス'
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
ms.openlocfilehash: 853944a8eab0698fae6a12cace4ce9426ada8f3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324998"
---
# <a name="condition_variable_any-class"></a>condition_variable_any クラス

`condition_variable_any` 型を持つイベントを待機するには、クラス `mutex` を使用します。

## <a name="syntax"></a>構文

```cpp
class condition_variable_any;
```

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|名前|説明|
|-|-|
|[condition_variable_any](#condition_variable_any)|`condition_variable_any` オブジェクトを構築します。|

### <a name="functions"></a>関数

|名前|説明|
|-|-|
|[notify_all](#notify_all)|`condition_variable_any` オブジェクトを待機しているすべてのスレッドのブロックを解除します。|
|[notify_one](#notify_one)|`condition_variable_any` オブジェクトを待機しているスレッドの 1 つのブロックを解除します。|
|[wait](#wait)|スレッドをブロックします。|
|[wait_for](#wait_for)|スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。|
|[wait_until](#wait_until)|スレッドをブロックし、スレッドがブロック解除される最大の時刻を設定します。|

## <a name="condition_variable_any"></a><a name="condition_variable_any"></a> condition_variable_any

`condition_variable_any` オブジェクトを構築します。

```cpp
condition_variable_any();
```

### <a name="remarks"></a>解説

十分なメモリが使用できない場合、コンストラクターは `not_enough_memory` エラー コードがある [system_error](../standard-library/system-error-class.md) オブジェクトをスローします。 他のリソースをいくつか使用できないためにオブジェクトが構築できない場合、コンストラクターは `system_error` エラー コードがある `resource_unavailable_try_again` オブジェクトをスローします。

## <a name="notify_all"></a><a name="notify_all"></a> notify_all

`condition_variable_any` オブジェクトを待機しているすべてのスレッドのブロックを解除します。

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a><a name="notify_one"></a> notify_one

`condition_variable_any` オブジェクトを待機しているスレッドの 1 つのブロックを解除します。

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a><a name="wait"></a> 待機

スレッドをブロックします。

```cpp
template <class Lock>
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```

### <a name="parameters"></a>パラメーター

*Lck*\
任意の型の `mutex` オブジェクト。

*Pred*\
またはを返す任意の式 **`true`** **`false`** 。

### <a name="remarks"></a>解説

最初のメソッドは `condition_variable_any` オブジェクトが [notify_one](../standard-library/condition-variable-class.md#notify_one) または [notify_all](../standard-library/condition-variable-class.md#notify_all) への呼び出しによって通知されるまでブロックします。 また、擬似的に開始することもできます。

実際には、2 つ目のメソッドは次のコードを実行します。

```cpp
while (!Pred())
    wait(Lck);
```

## <a name="wait_for"></a><a name="wait_for"></a> wait_for

スレッドをブロックし、スレッドがブロック解除されるまでの時間間隔を設定します。

```cpp
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```

### <a name="parameters"></a>パラメーター

*Lck*\
任意の型の `mutex` オブジェクト。

*Rel_time*\
スレッドが開始するまでの時間の長さを指定する `chrono::duration` オブジェクト。

*Pred*\
またはを返す任意の式 **`true`** **`false`** 。

### <a name="return-value"></a>戻り値

最初のメソッドは、 `cv_status::timeout` *Rel_time* が経過したときに待機が終了した場合、を返します。 それ以外の場合、メソッドは `cv_status::no_timeout` を返します。

2番目のメソッドは、 *Pred* の値を返します。

### <a name="remarks"></a>解説

最初のメソッドは、 `condition_variable_any` オブジェクトが [notify_one](../standard-library/condition-variable-class.md#notify_one) または [notify_all](../standard-library/condition-variable-class.md#notify_all)の呼び出しによって通知されるまで、または *Rel_time* が経過するまでブロックします。 また、擬似的に開始することもできます。

実際には、2 つ目のメソッドは次のコードを実行します。

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a><a name="wait_until"></a> wait_until

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

*Lck*\
ミューテックス オブジェクト。

*Abs_time*\
[chrono::time_point](../standard-library/time-point-class.md) オブジェクト。

*Pred*\
またはを返す任意の式 **`true`** **`false`** 。

### <a name="return-value"></a>戻り値

`cv_status` `cv_status::timeout` *Abs_time* が経過したときに待機が終了した場合、型を返すメソッドはを返します。 それ以外の場合、メソッドは `cv_status::no_timeout` を返します。

を返すメソッドは、 **`bool`** *Pred* の値を返します。

### <a name="remarks"></a>解説

最初のメソッドは、 `condition_variable` オブジェクトが [notify_one](../standard-library/condition-variable-class.md#notify_one) または [notify_all](../standard-library/condition-variable-class.md#notify_all)の呼び出しによって通知されるまで、または *Abs_time* するまでブロックします。 また、擬似的に開始することもできます。

実際には、2 つ目のメソッドは次のコードを実行します。

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

3 つ目のメソッドと 4 つ目のメソッドは、`xtime` 型のオブジェクトへのポインターを使用して、`chrono::time_point` オブジェクトを置き換えます。 `xtime` オブジェクトは、シグナルを待機する時間の最大値を指定します。
