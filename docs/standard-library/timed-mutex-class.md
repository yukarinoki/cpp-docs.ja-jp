---
title: timed_mutex クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::timed_mutex
- mutex/std::timed_mutex::timed_mutex
- mutex/std::timed_mutex::lock
- mutex/std::timed_mutex::try_lock
- mutex/std::timed_mutex::try_lock_for
- mutex/std::timed_mutex::try_lock_until
- mutex/std::timed_mutex::unlock
dev_langs:
- C++
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::timed_mutex [C++]
- std::timed_mutex [C++], timed_mutex
- std::timed_mutex [C++], lock
- std::timed_mutex [C++], try_lock
- std::timed_mutex [C++], try_lock_for
- std::timed_mutex [C++], try_lock_until
- std::timed_mutex [C++], unlock
ms.workload:
- cplusplus
ms.openlocfilehash: a4dc22ed8676c720dd8bde5c8f424915dfa8fe40
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="timedmutex-class"></a>timed_mutex クラス

*timed mutex 型*を表します。 この型のオブジェクトは、プログラム内での時間制限ブロックを使った相互排他を強制するのに使用されます。

## <a name="syntax"></a>構文

```cpp
class timed_mutex;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[timed_mutex](#timed_mutex)|ロックされていない `timed_mutex` オブジェクトを構築します。|
|[timed_mutex::~timed_mutex デストラクター](#dtortimed_mutex_destructor)|`timed_mutex` オブジェクトによって使用されているすべてのリソースを解放します。|

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

## <a name="lock"></a>  timed_mutex::lock

呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。

```cpp
void lock();
```

### <a name="remarks"></a>コメント

呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。

## <a name="timed_mutex"></a>  timed_mutex::timed_mutex コンストラクター

ロックされていない `timed_mutex` オブジェクトを構築します。

```cpp
timed_mutex();
```

## <a name="dtortimed_mutex_destructor"></a>  timed_mutex::~timed_mutex デストラクター

`mutex` オブジェクトによって使用されているすべてのリソースを解放します。

```cpp
~timed_mutex();
```

### <a name="remarks"></a>コメント

デストラクターの実行時にオブジェクトがロックされる場合の動作は未定義です。

## <a name="try_lock"></a>  timed_mutex::try_lock

ブロックせずに `mutex` の所有権を取得しようとします。

```cpp
bool try_lock();
```

### <a name="return-value"></a>戻り値

メソッドが `true` の所有権の取得に成功した場合は `mutex` を返します。それ以外の場合は `false` を返します。

### <a name="remarks"></a>コメント

呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。

## <a name="try_lock_for"></a>  timed_mutex::try_lock_for

ブロックせずに `mutex` の所有権を取得しようとします。

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>パラメーター

`Rel_time` A [:duration](../standard-library/duration-class.md)の所有権の取得を試行する時間の最大サイズを指定するオブジェクト、`mutex`です。

### <a name="return-value"></a>戻り値

メソッドが `true` の所有権の取得に成功した場合は `mutex` を返します。それ以外の場合は `false` を返します。

### <a name="remarks"></a>コメント

呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。

## <a name="try_lock_until"></a>  timed_mutex::try_lock_until

ブロックせずに `mutex` の所有権を取得しようとします。

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>パラメーター

`Abs_time` その後、メソッドを止めるの所有権の取得のしきい値を指定する時点、`mutex`です。

### <a name="return-value"></a>戻り値

メソッドが `true` の所有権の取得に成功した場合は `mutex` を返します。それ以外の場合は `false` を返します。

### <a name="remarks"></a>コメント

呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。

## <a name="unlock"></a>  timed_mutex::unlock

`mutex` の所有権を解放します。

```cpp
void unlock();
```

### <a name="remarks"></a>コメント

呼び出しスレッドが `mutex` を所有していない場合の動作は未定義です。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
