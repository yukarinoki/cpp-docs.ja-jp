---
title: unique_lock クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::unique_lock
dev_langs:
- C++
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9888b847c3e52cd8b6a034e95e35ca73933acd3f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="uniquelock-class"></a>unique_lock クラス

`mutex` のロックとロック解除を管理するオブジェクトを作成するためにインスタンス化できるテンプレートを表します。

## <a name="syntax"></a>構文

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>コメント

テンプレート引数 `Mutex` には *mutex 型*を指定する必要があります。

内部的には、`unique_lock` には関連付けられた `mutex` オブジェクトへのポインターと、現在のスレッドが `mutex` を所有するかどうかを示す `bool` が格納されます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`mutex_type`|テンプレート引数 `Mutex` のシノニム。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[unique_lock](#unique_lock)|`unique_lock` オブジェクトを構築します。|
|[~unique_lock デストラクター](#dtorunique_lock_destructor)|`unique_lock` オブジェクトに関連付けられたすべてのリソースを解放します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[lock](#lock)|呼び出しスレッドが、関連付けられた `mutex` の所有権を取得するまで、そのスレッドをブロックします。|
|[mutex](#mutex)|格納されている、関連付けられた `mutex` へのポインターを取得します。|
|[owns_lock](#owns_lock)|呼び出し元のスレッドが、関連付けられた `mutex` を所有しているかどうかを指定します。|
|[release](#release)|`mutex` から `unique_lock` オブジェクトの関連付けを解除します。|
|[swap](#swap)|関連付けられた `mutex` と所有状態を、指定されたオブジェクトのものと入れ替えます。|
|[try_lock](#try_lock)|ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。|
|[try_lock_for](#try_lock_for)|ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。|
|[try_lock_until](#try_lock_until)|ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。|
|[unlock](#unlock)|関連付けられた `mutex` の所有権を解放します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[operator bool](#op_bool)|呼び出し元のスレッドに、関連付けられた `mutex` の所有権があるかどうかを指定します。|
|[operator=](#op_eq)|格納された `mutex` ポインターと所有状態を、指定されたオブジェクトからコピーします。|

## <a name="inheritance-hierarchy"></a>継承階層

`unique_lock`

## <a name="requirements"></a>要件

**ヘッダー:** \<ミュー テックス >

**名前空間:** std

## <a name="lock"></a>  lock

呼び出しスレッドが、関連付けられた `mutex` の所有権を取得するまで、そのスレッドをブロックします。

```cpp
void lock();
```

### <a name="remarks"></a>コメント

格納された `mutex` ポインターが `null` である場合、このメソッドはエラー コード `operation_not_permitted` で [system_error](../standard-library/system-error-class.md) をスローします。

呼び出し元のスレッドが、関連付けられた `mutex` を既に所有している場合、このメソッドはエラー コード `resource_deadlock_would_occur` で `system_error` をスローします。

それ以外の場合、このメソッドは関連付けられた `mutex` に対して `lock` を呼び出し、内部スレッド所有権フラグを `true` に設定します。

## <a name="mutex"></a>  mutex

格納されている、関連付けられた `mutex` へのポインターを取得します。

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="op_bool"></a>  operator bool

呼び出し元のスレッドに、関連付けられたミューテックスの所有権があるかどうかを指定します。

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>戻り値

スレッドがミューテックスを所有している場合は `true`、それ以外は `false`。

## <a name="op_eq"></a>  operator=

格納された `mutex` ポインターと所有状態を、指定されたオブジェクトからコピーします。

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>パラメーター

`Other` A`unique_lock`オブジェクト。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>コメント

呼び出し元のスレッドが前に関連付けられていた `mutex` を所有している場合、このメソッドでは、`mutex` の `unlock` を呼び出す前に、新しい値を割り当てます。

コピーの後、このメソッドは、既定で構築される状態に `Other` を設定します。

## <a name="owns_lock"></a>  owns_lock

呼び出し元のスレッドが、関連付けられた `mutex` を所有しているかどうかを指定します。

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>戻り値

スレッドが `mutex` を所有している場合は `true`、それ以外は `false`。

## <a name="release"></a>  release

`mutex` から `unique_lock` オブジェクトの関連付けを解除します。

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>戻り値

格納された `mutex` ポインターの以前の値。

### <a name="remarks"></a>コメント

このメソッドでは、格納された `mutex` ポインターの値を 0 と設定し、内部の `mutex` 所有権フラグを `false` に設定します。

## <a name="swap"></a>  swap

関連付けられた `mutex` と所有状態を、指定されたオブジェクトのものと入れ替えます。

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>パラメーター

`Other` A`unique_lock`オブジェクト。

## <a name="try_lock"></a>  try_lock

ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>戻り値

メソッドが `true` の所有権の取得に成功した場合は `mutex` を返します。それ以外の場合は `false` を返します。

### <a name="remarks"></a>コメント

格納された `mutex` ポインターが `null` である場合、このメソッドはエラー コード `operation_not_permitted` で [system_error](../standard-library/system-error-class.md) をスローします。

呼び出し元のスレッドが既に `mutex` を所有している場合、このメソッドはエラー コード `resource_deadlock_would_occur` で `system_error` をスローします。

## <a name="try_lock_for"></a>  try_lock_for

ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>パラメーター

`Rel_time` A [:duration](../standard-library/duration-class.md)の所有権の取得を試行する時間の最大サイズを指定するオブジェクト、`mutex`です。

### <a name="return-value"></a>戻り値

メソッドが `true` の所有権の取得に成功した場合は `mutex` を返します。それ以外の場合は `false` を返します。

### <a name="remarks"></a>コメント

格納された `mutex` ポインターが `null` である場合、このメソッドはエラー コード `operation_not_permitted` で [system_error](../standard-library/system-error-class.md) をスローします。

呼び出し元のスレッドが既に `mutex` を所有している場合、このメソッドはエラー コード `resource_deadlock_would_occur` で `system_error` をスローします。

## <a name="try_lock_until"></a>  try_lock_until

ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>パラメーター

`Abs_time` その後、メソッドを止めるの所有権の取得のしきい値を指定する時点、`mutex`です。

### <a name="return-value"></a>戻り値

メソッドが `true` の所有権の取得に成功した場合は `mutex` を返します。それ以外の場合は `false` を返します。

### <a name="remarks"></a>コメント

格納された `mutex` ポインターが `null` である場合、このメソッドはエラー コード `operation_not_permitted` で [system_error](../standard-library/system-error-class.md) をスローします。

呼び出し元のスレッドが既に `mutex` を所有している場合、このメソッドはエラー コード `resource_deadlock_would_occur` で `system_error` をスローします。

## <a name="unique_lock"></a>  unique_lock コンストラクター

`unique_lock` オブジェクトを構築します。

```cpp
unique_lock() noexcept;
unique_lock(unique_lock&& Other) noexcept;
explicit unique_lock(mutex_type& Mtx);

unique_lock(mutex_type& Mtx, adopt_lock_t Adopt);

unique_lock(mutex_type& Mtx, defer_lock_t Defer) noexcept;
unique_lock(mutex_type& Mtx, try_to_lock_t Try);

template <class Rep, class Period>
unique_lock(mutex_type& Mtx,
    const chrono::duration<Rep, Period>
Rel_time);

template <class Clock, class Duration>
unique_lock(mutex_type& Mtx,
    const chrono::time_point<Clock, Duration>
Abs_time);

unique_lock(mutex_type& Mtx,
    const xtime* Abs_time) noexcept;
```

### <a name="parameters"></a>パラメーター

`Mtx` Mutex 型オブジェクト。

`Rel_time` A [:duration](../standard-library/duration-class.md)の所有権の取得を試行する時間の最大サイズを指定するオブジェクト、`mutex`です。

`Abs_time` その後、メソッドを止めるの所有権の取得のしきい値を指定する時点、`mutex`です。

`Other` A`unique_lock`オブジェクト。

### <a name="remarks"></a>コメント

1 番目のコンストラクターは、関連付けられたミューテックス ポインター値が 0 であるオブジェクトを構築します。

2 番目のコンストラクターによって、関連付けられたミューテックスの状態が `Other` に移動します。 移動した後、`Other` はミューテックスと関連付けられなくなります。

残りのコンストラクターは、格納された `mutex` ポインターとして & `Mtx` を格納します。 `mutex` の所有権は、2 番目の引数 (存在する場合) によって決まります。

|||
|-|-|
|`No argument`|所有権は、関連付けられた `mutex` オブジェクトに対して `lock` メソッドを呼び出すことによって取得します。|
|`Adopt`|所有権があると見なされます。 このコンストラクターを呼び出すとき、`Mtx` がロックされている必要があります。|
|`Defer`|呼び出し元のスレッドには `mutex` の所有権はないと見なされます。 このコンストラクターを呼び出すとき、`Mtx` がロックされていない必要があります。|
|`Try`|所有権は、関連付けられた `mutex` オブジェクトに対して `try_lock` を呼び出すことによって決定されます。 このコンストラクターでは何もスローされません。|
|`Rel_time`|所有権は、`try_lock_for(Rel_time)` を呼び出すことによって決定されます。|
|`Abs_time`|所有権は、`try_lock_until(Abs_time)` を呼び出すことによって決定されます。|

## <a name="dtorunique_lock_destructor"></a>  ~unique_lock デストラクター

`unique_lock` オブジェクトに関連付けられたすべてのリソースを解放します。

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>コメント

呼び出し元のスレッドが、関連付けられた `mutex` を所有している場合、デストラクターでは、`mutex` オブジェクトに対するロック解除を呼び出すことによって所有権を解放します。

## <a name="unlock"></a>  unlock

関連付けられた `mutex` の所有権を解放します。

```cpp
void unlock();
```

### <a name="remarks"></a>コメント

呼び出し元のスレッドが、関連付けられた `mutex` を所有していない場合、このメソッドはエラー コード `operation_not_permitted` で [system_error](../standard-library/system-error-class.md) をスローします。

それ以外の場合、このメソッドは関連付けられた `mutex` に対して `unlock` を呼び出し、内部スレッド所有権フラグを `false` に設定します。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
