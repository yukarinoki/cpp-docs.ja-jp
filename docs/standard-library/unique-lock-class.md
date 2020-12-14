---
description: '詳細情報: unique_lock クラス'
title: unique_lock クラス
ms.date: 11/04/2016
f1_keywords:
- mutex/std::unique_lock
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
ms.openlocfilehash: 6e7f5ddadce00814196e630b27570e21176c0e62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243719"
---
# <a name="unique_lock-class"></a>unique_lock クラス

`mutex` のロックとロック解除を管理するオブジェクトを作成するためにインスタンス化できるテンプレートを表します。

## <a name="syntax"></a>構文

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>解説

テンプレート引数 `Mutex` には *mutex 型* を指定する必要があります。

内部的には、には、 `unique_lock` 関連付けられたオブジェクトへのポインター `mutex` と、 **`bool`** 現在のスレッドがを所有しているかどうかを示すが格納され `mutex` ます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`mutex_type`|テンプレート引数 `Mutex` のシノニム。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[unique_lock](#unique_lock)|`unique_lock` オブジェクトを構築します。|
|[~ unique_lock デストラクター](#dtorunique_lock_destructor)|`unique_lock` オブジェクトに関連付けられたすべてのリソースを解放します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[lock](#lock)|呼び出しスレッドが、関連付けられた `mutex` の所有権を取得するまで、そのスレッドをブロックします。|
|[ロック](#mutex)|格納されている、関連付けられた `mutex` へのポインターを取得します。|
|[owns_lock](#owns_lock)|呼び出し元のスレッドが、関連付けられた `mutex` を所有しているかどうかを指定します。|
|[解除](#release)|`mutex` から `unique_lock` オブジェクトの関連付けを解除します。|
|[スワップ](#swap)|関連付けられた `mutex` と所有状態を、指定されたオブジェクトのものと入れ替えます。|
|[try_lock](#try_lock)|ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。|
|[try_lock_for](#try_lock_for)|ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。|
|[try_lock_until](#try_lock_until)|ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。|
|[ロック](#unlock)|関連付けられた `mutex` の所有権を解放します。|

### <a name="public-operators"></a>パブリック演算子

|名前|説明|
|----------|-----------------|
|[bool 演算子](#op_bool)|呼び出し元のスレッドに、関連付けられた `mutex` の所有権があるかどうかを指定します。|
|[operator =](#op_eq)|格納された `mutex` ポインターと所有状態を、指定されたオブジェクトからコピーします。|

## <a name="inheritance-hierarchy"></a>継承階層

*unique_lock*

## <a name="requirements"></a>要件

**ヘッダー:**\<mutex>

**名前空間:** std

## <a name="lock"></a><a name="lock"></a> 制限

呼び出しスレッドが、関連付けられた `mutex` の所有権を取得するまで、そのスレッドをブロックします。

```cpp
void lock();
```

### <a name="remarks"></a>解説

格納されている `mutex` ポインターが NULL の場合、このメソッドはのエラーコードを持つ [system_error](../standard-library/system-error-class.md) をスローし `operation_not_permitted` ます。

呼び出し元のスレッドが、関連付けられた `mutex` を既に所有している場合、このメソッドはエラー コード `resource_deadlock_would_occur` で `system_error` をスローします。

それ以外の場合、このメソッドは `lock` 、関連付けられたに対してを呼び出し、 `mutex` 内部スレッド所有権フラグをに設定し **`true`** ます。

## <a name="mutex"></a><a name="mutex"></a> ロック

格納されている、関連付けられた `mutex` へのポインターを取得します。

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="operator-bool"></a><a name="op_bool"></a> bool 演算子

呼び出し元のスレッドに、関連付けられたミューテックスの所有権があるかどうかを指定します。

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>戻り値

**`true`** スレッドがミューテックスを所有している場合は。それ以外の場合は **`false`** 。

## <a name="operator"></a><a name="op_eq"></a> operator =

格納された `mutex` ポインターと所有状態を、指定されたオブジェクトからコピーします。

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>パラメーター

*他の*\
`unique_lock` オブジェクト。

### <a name="return-value"></a>戻り値

`*this`

### <a name="remarks"></a>解説

呼び出し元のスレッドが前に関連付けられていた `mutex` を所有している場合、このメソッドでは、`mutex` の `unlock` を呼び出す前に、新しい値を割り当てます。

コピー後、このメソッドは、 *他の* を既定で構築された状態に設定します。

## <a name="owns_lock"></a><a name="owns_lock"></a> owns_lock

呼び出し元のスレッドが、関連付けられた `mutex` を所有しているかどうかを指定します。

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>戻り値

**`true`** スレッドがを所有している場合は `mutex` 。それ以外の場合は **`false`** 。

## <a name="release"></a><a name="release"></a> 解除

`mutex` から `unique_lock` オブジェクトの関連付けを解除します。

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>戻り値

格納された `mutex` ポインターの以前の値。

### <a name="remarks"></a>解説

このメソッドは、格納されているポインターの値を `mutex` 0 に設定し、内部の `mutex` 所有権フラグをに設定し **`false`** ます。

## <a name="swap"></a><a name="swap"></a> フォト

関連付けられた `mutex` と所有状態を、指定されたオブジェクトのものと入れ替えます。

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>パラメーター

*他の*\
`unique_lock` オブジェクト。

## <a name="try_lock"></a><a name="try_lock"></a> try_lock

ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>戻り値

**`true`** メソッドがの所有権を正常に取得した場合は `mutex` 。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

格納されている `mutex` ポインターが NULL の場合、メソッドはのエラーコードを持つ [system_error](../standard-library/system-error-class.md) をスローし `operation_not_permitted` ます。

呼び出し元のスレッドが既に `mutex` を所有している場合、このメソッドはエラー コード `resource_deadlock_would_occur` で `system_error` をスローします。

## <a name="try_lock_for"></a><a name="try_lock_for"></a> try_lock_for

ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>パラメーター

*Rel_time*\
メソッドが `mutex` の所有権の取得を試行する時間について、その最大値を指定する [chrono::duration](../standard-library/duration-class.md) オブジェクト。

### <a name="return-value"></a>戻り値

**`true`** メソッドがの所有権を正常に取得した場合は `mutex` 。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

格納されている `mutex` ポインターが NULL の場合、メソッドはのエラーコードを持つ [system_error](../standard-library/system-error-class.md) をスローし `operation_not_permitted` ます。

呼び出し元のスレッドが既に `mutex` を所有している場合、このメソッドはエラー コード `resource_deadlock_would_occur` で `system_error` をスローします。

## <a name="try_lock_until"></a><a name="try_lock_until"></a> try_lock_until

ブロックせずに関連付けられた `mutex` の所有権を取得しようとします。

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>パラメーター

*Abs_time*\
メソッドが `mutex` の所有権の取得を止めるしきい値を指定する時点。

### <a name="return-value"></a>戻り値

**`true`** メソッドがの所有権を正常に取得した場合は `mutex` 。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

格納されている `mutex` ポインターが NULL の場合、メソッドはのエラーコードを持つ [system_error](../standard-library/system-error-class.md) をスローし `operation_not_permitted` ます。

呼び出し元のスレッドが既に `mutex` を所有している場合、このメソッドはエラー コード `resource_deadlock_would_occur` で `system_error` をスローします。

## <a name="unique_lock-constructor"></a><a name="unique_lock"></a> unique_lock コンストラクター

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

*Mtx.exe*\
mutex 型オブジェクト。

*Rel_time*\
メソッドが `mutex` の所有権の取得を試行する時間について、その最大値を指定する [chrono::duration](../standard-library/duration-class.md) オブジェクト。

*Abs_time*\
メソッドが `mutex` の所有権の取得を止めるしきい値を指定する時点。

*他の*\
`unique_lock` オブジェクト。

### <a name="remarks"></a>解説

1 番目のコンストラクターは、関連付けられたミューテックス ポインター値が 0 であるオブジェクトを構築します。

2番目のコンストラクターは、関連する mutex の状態を *Other* に移動します。 移動後、 *他の* はミューテックスと関連付けられなくなります。

残りのコンストラクターは、格納されているポインターとして & *mtx.exe* を格納し `mutex` ます。 `mutex` の所有権は、2 番目の引数 (存在する場合) によって決まります。

|名前|説明|
|-|-|
|`No argument`|所有権は、関連付けられた `mutex` オブジェクトに対して `lock` メソッドを呼び出すことによって取得します。|
|`Adopt`|所有権があると見なされます。 このコンストラクターを呼び出すとき、`Mtx` がロックされている必要があります。|
|`Defer`|呼び出し元のスレッドには `mutex` の所有権はないと見なされます。 このコンストラクターを呼び出すとき、`Mtx` がロックされていない必要があります。|
|`Try`|所有権は、関連付けられた `mutex` オブジェクトに対して `try_lock` を呼び出すことによって決定されます。 このコンストラクターでは何もスローされません。|
|`Rel_time`|所有権は、`try_lock_for(Rel_time)` を呼び出すことによって決定されます。|
|`Abs_time`|所有権は、`try_lock_until(Abs_time)` を呼び出すことによって決定されます。|

## <a name="unique_lock-destructor"></a><a name="dtorunique_lock_destructor"></a>  ~unique_lock デストラクター

`unique_lock` オブジェクトに関連付けられたすべてのリソースを解放します。

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>解説

呼び出し元のスレッドが、関連付けられた `mutex` を所有している場合、デストラクターでは、`mutex` オブジェクトに対するロック解除を呼び出すことによって所有権を解放します。

## <a name="unlock"></a><a name="unlock"></a> ロック

関連付けられた `mutex` の所有権を解放します。

```cpp
void unlock();
```

### <a name="remarks"></a>解説

呼び出し元のスレッドが、関連付けられた `mutex` を所有していない場合、このメソッドはエラー コード `operation_not_permitted` で [system_error](../standard-library/system-error-class.md) をスローします。

それ以外の場合、このメソッドは `unlock` 、関連付けられたに対してを呼び出し、 `mutex` 内部スレッド所有権フラグをに設定し **`false`** ます。

## <a name="see-also"></a>関連項目

[ヘッダーファイルのリファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
