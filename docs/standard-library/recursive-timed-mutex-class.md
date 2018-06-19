---
title: recursive_timed_mutex クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::lock
- mutex/std::recursive_timed_mutex::try_lock
- mutex/std::recursive_timed_mutex::try_lock_for
- mutex/std::recursive_timed_mutex::try_lock_until
- mutex/std::recursive_timed_mutex::unlock
dev_langs:
- C++
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::recursive_timed_mutex [C++]
- std::recursive_timed_mutex [C++], recursive_timed_mutex
- std::recursive_timed_mutex [C++], lock
- std::recursive_timed_mutex [C++], try_lock
- std::recursive_timed_mutex [C++], try_lock_for
- std::recursive_timed_mutex [C++], try_lock_until
- std::recursive_timed_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: 9b4a87cadedb11368d7803231b96d0f7a5acfb99
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863713"
---
# <a name="recursivetimedmutex-class"></a>recursive_timed_mutex クラス

*timed mutex 型*を表します。 この型のオブジェクトは、プログラム内での時間制限ブロックを使った相互排他を強制するのに使用されます。 [timed_mutex](../standard-library/timed-mutex-class.md) 型のオブジェクトとは異なり、`recursive_timed_mutex` オブジェクトにロック メソッドを呼び出すことによる影響は詳細に定義されています。

## <a name="syntax"></a>構文

```cpp
class recursive_timed_mutex;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[recursive_timed_mutex](#recursive_timed_mutex)|ロックされていない `recursive_timed_mutex` オブジェクトを構築します。|
|[~recursive_timed_mutex デストラクター](#dtorrecursive_timed_mutex_destructor)|`recursive_timed_mutex` オブジェクトによって使用されているすべてのリソースを解放します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[lock](#lock)|呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。|
|[try_lock](#try_lock)|ブロックせずに `mutex` の所有権を取得しようとします。|
|[try_lock_for](#try_lock_for)|指定した時間のあいだ `mutex` の所有権の取得を試みます。|
|[try_lock_until](#try_lock_until)|指定した時刻まで `mutex` の所有権の取得を試みます。|
|[unlock](#unlock)|`mutex` の所有権を解放します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<ミュー テックス >

**名前空間:** std

## <a name="lock"></a>  lock

呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。

```cpp
void lock();
```

### <a name="remarks"></a>コメント

呼び出しスレッドが既に `mutex` を所有している場合、メソッドが直ちに返され、以前のロックは有効のままになります。

## <a name="recursive_timed_mutex"></a>  recursive_timed_mutex コンストラクター

ロックされていない `recursive_timed_mutex` オブジェクトを構築します。

```cpp
recursive_timed_mutex();
```

## <a name="dtorrecursive_timed_mutex_destructor"></a>  ~recursive_timed_mutex デストラクター

`recursive_timed_mutex` オブジェクトによって使用されるすべてのリソースを解放します。

```cpp
~recursive_timed_mutex();
```

### <a name="remarks"></a>コメント

デストラクターの実行時にオブジェクトがロックされる場合の動作は未定義です。

## <a name="try_lock"></a>  try_lock

ブロックせずに `mutex` の所有権を取得しようとします。

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>戻り値

メソッドが `mutex` の所有権を正常に取得した場合、または呼び出しスレッドがすでに `mutex` を所有している場合は `true`、それ以外の場合は `false` です。

### <a name="remarks"></a>コメント

呼び出しスレッドが既に `mutex` を所有している場合、関数が直ちに `true` を返し、以前のロックは有効のままになります。

## <a name="try_lock_for"></a>  try_lock_for

ブロックせずに `mutex` の所有権を取得しようとします。

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>パラメーター

`Rel_time` A [:duration](../standard-library/duration-class.md)の所有権の取得を試行する時間の最大サイズを指定するオブジェクト、`mutex`です。

### <a name="return-value"></a>戻り値

メソッドが `mutex` の所有権を正常に取得した場合、または呼び出し元のスレッドがすでに `mutex` を所有している場合は `true`、それ以外の場合は `false` です。

### <a name="remarks"></a>コメント

呼び出しスレッドが既に `mutex` を所有している場合、メソッドが直ちに `true` を返し、以前のロックは有効のままになります。

## <a name="try_lock_until"></a>try_lock_until

ブロックせずに `mutex` の所有権を取得しようとします。

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>パラメーター

`Abs_time` その後、メソッドを止めるの所有権の取得のしきい値を指定する時点、`mutex`です。

### <a name="return-value"></a>戻り値

メソッドが `mutex` の所有権を正常に取得した場合、または呼び出し元のスレッドがすでに `mutex` を所有している場合は `true`、それ以外の場合は `false` です。

### <a name="remarks"></a>コメント

呼び出しスレッドが既に `mutex` を所有している場合、メソッドが直ちに `true` を返し、以前のロックは有効のままになります。

## <a name="unlock"></a>  unlock

`mutex` の所有権を解放します。

```cpp
void unlock();
```

### <a name="remarks"></a>コメント

このメソッドが `mutex` の所有権を開放するのは、[lock](#lock)、[try_lock](#try_lock)、[try_lock_for](#try_lock_for)、および [try_lock_until](#try_lock_until) が `recursive_timed_mutex` オブジェクト上で正常に呼び出されたのと同じ回数だけ呼び出された後のみです。

呼び出しスレッドが `mutex` を所有していない場合の動作は未定義です。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
