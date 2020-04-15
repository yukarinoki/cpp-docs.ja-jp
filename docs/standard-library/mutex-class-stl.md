---
title: mutex クラス (C++ 標準ライブラリ)| Microsoft Docs
ms.date: 11/04/2016
f1_keywords:
- mutex/std::mutex
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
helpviewer_keywords:
- std::mutex [C++]
- std::mutex [C++], mutex
- std::mutex [C++], lock
- std::mutex [C++], native_handle
- std::mutex [C++], try_lock
- std::mutex [C++], unlock
ms.openlocfilehash: 84e6e3a46903a204444df9886556ae2c563304a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364845"
---
# <a name="mutex-class-c-standard-library"></a>mutex クラス (C++ 標準ライブラリ)

*ミューテックス型*を表します。 この型のオブジェクトを使用して、プログラム内で相互排他を適用できます。

## <a name="syntax"></a>構文

```cpp
class mutex;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[ミュー テックス](#mutex)|`mutex` オブジェクトを構築します。|
|[mutex::~mutex デストラクター](#dtormutex_destructor)|`mutex` オブジェクトで使用されたすべてのリソースを解放します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[ロック](#lock)|呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。|
|[native_handle](#native_handle)|ミューテックス ハンドルを表す実装固有の型を返します。|
|[try_lock](#try_lock)|ブロックせずに `mutex` の所有権を取得しようとします。|
|[ロック 解除](#unlock)|`mutex` の所有権を解放します。|

## <a name="requirements"></a>必要条件

**ヘッダー:**\<ミューテックス>

**名前空間:** std

## <a name="mutexlock"></a><a name="lock"></a>ミューテックス::ロック

呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。

```cpp
void lock();
```

### <a name="remarks"></a>解説

呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。

## <a name="mutexmutex-constructor"></a><a name="mutex"></a>ミューテックス::ミューテックスコンストラクタ

ロックされていない `mutex` オブジェクトを構築します。

```cpp
constexpr mutex() noexcept;
```

## <a name="mutexmutex-destructor"></a><a name="dtormutex_destructor"></a>ミューテックス::~ミューテックスデストラクタ

`mutex` オブジェクトによって使用されるすべてのリソースを解放します。

```cpp
~mutex();
```

### <a name="remarks"></a>解説

デストラクターの実行時にオブジェクトがロックされる場合の動作は未定義です。

## <a name="mutexnative_handle"></a><a name="native_handle"></a>ミューテックス::native_handle

ミューテックス ハンドルを表す実装固有の型を返します。 ミューテックス ハンドルは、実装固有の方法で使用できます。

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>戻り値

`native_handle_type` は、`void *` としてキャストされる `Concurrency::critical_section *` と定義されます。

## <a name="mutextry_lock"></a><a name="try_lock"></a>ミューテックス::try_lock

ブロックせずに `mutex` の所有権を取得しようとします。

```cpp
bool try_lock();
```

### <a name="return-value"></a>戻り値

メソッドがの所有権を正常に取得する場合は`mutex` **true。** それ以外の場合**は false。**

### <a name="remarks"></a>解説

呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。

## <a name="mutexunlock"></a><a name="unlock"></a>ミューテックス::ロック解除

`mutex` の所有権を解放します。

```cpp
void unlock();
```

### <a name="remarks"></a>解説

呼び出しスレッドが `mutex` を所有していない場合の動作は未定義です。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)\
[\<ミューテックス>](../standard-library/mutex.md)
