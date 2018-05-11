---
title: '&lt;shared_mutex&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <shared_mutex>
- shared_mutex/std::swap
- shared_mutex/std::shared_lock
- shared_mutex/std::shared_lock::shared_lock
- shared_mutex/std::shared_lock::operator=
- shared_mutex/std::shared_lock::operator =
- shared_mutex/std::shared_lock::lock
- shared_mutex/std::shared_lock::try_lock
- shared_mutex/std::shared_lock::try_lock_for
- shared_mutex/std::shared_lock::try_lock_until
- shared_mutex/std::shared_lock::unlock
- shared_mutex/std::shared_lock::swap
- shared_mutex/std::shared_lock::release
- shared_mutex/std::shared_lock::owns_lock
- shared_mutex/std::shared_lock::operator bool
- shared_mutex/std::shared_lock::mutex
- shared_mutex/std::shared_mutex
- shared_mutex/std::shared_mutex::native_handle_type
- shared_mutex/std::shared_mutex::shared_mutex
- shared_mutex/std::shared_mutex::operator=
- shared_mutex/std::shared_mutex::operator =
- shared_mutex/std::shared_mutex::lock
- shared_mutex/std::shared_mutex::try_lock
- shared_mutex/std::shared_mutex::unlock
- shared_mutex/std::shared_mutex::lock_shared
- shared_mutex/std::shared_mutex::try_lock_shared
- shared_mutex/std::shared_mutex::unlock_shared
- shared_mutex/std::shared_mutex::native_handle
- shared_mutex/std::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::operator=
- shared_mutex/std::shared_timed_mutex::operator =
- shared_mutex/std::shared_timed_mutex::lock
- shared_mutex/std::shared_timed_mutex::try_lock
- shared_mutex/std::shared_timed_mutex::try_lock_for
- shared_mutex/std::shared_timed_mutex::try_lock_until
- shared_mutex/std::shared_timed_mutex::unlock
- shared_mutex/std::shared_timed_mutex::lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared_for
- shared_mutex/std::shared_timed_mutex::try_lock_shared_until
- shared_mutex/std::shared_timed_mutex::unlock_shared
dev_langs:
- C++
ms.assetid: 0b37a97d-ee5d-4050-b29f-09db9f76beb3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4a9cd6c4533b3b59fdb3c5cab17ffaba071fb08
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltsharedmutex"></a>&lt;shared_mutex>

&lt;Shared_mutex > ヘッダーは、複数のスレッドがアクセスできる共有のデータの保護の同期プリミティブを提供します。 ミューテックス クラスで提供される排他アクセス制御だけでなく、共有ミューテックス クラスによって非排他的なアクセス用の複数のスレッドによる共有所有権も可能になります。 共有ミューテックスを使用して、競合状態を発生させず複数のスレッドで読み取ることができるリソースを制御できますが、共有ミューテックスは 1 つのスレッドによって排他的に書き込まれる必要があります。

ヘッダー &lt;shared_mutex > クラスを定義`shared_mutex`と`shared_timed_mutex`、テンプレート クラスは、 `shared_lock`、およびテンプレート関数は、`swap`のミュー テックスのサポートを共有します。

|クラス|説明|
|-------------|-----------------|
|[shared_mutex クラス](../standard-library/shared-mutex.md#class_shared_mutex)|1 つのエージェントによって排他的にロックされるか、または複数のエージェントで非排他的に共有される共有 mutex 型。|
|[shared_timed_mutex クラス](../standard-library/shared-mutex.md#class_shared_timed_mutex)|1 つのエージェントによって排他的にロックされるか、または複数のエージェントで非排他的に共有される共有 timed mutex 型。|
|[shared_lock クラス](../standard-library/shared-mutex.md#class_shared_lock)|時間指定のロック操作と複数のエージェントによる非排他的な共有をサポートするために共有ミューテックスをラップするテンプレート クラス。|

|関数|説明|
|---------------|-----------------|
|[swap](../standard-library/shared-mutex.md#function_swap)|関数のパラメーターによって参照される共有ミューテックス オブジェクトの内容を交換します。|

## <a name="syntax"></a>構文

```cpp
namespace std {
    class shared_mutex;
    class shared_timed_mutex;
    template <class Mutex>
class shared_lock;
    template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
}
```

## <a name="remarks"></a>コメント

クラス `shared_mutex` のインスタンスは、*共有 mutex 型*、つまり、スコープ内でのミューテックスの共有所有権を制御する型です。 共有 mutex 型は、mutex 型および共有の非排他的な所有権をサポートするためのメンバーの要件をすべて満たしています。

共有 mutex 型は、追加のメソッド `lock_shared`、`unlock_shared`、および `try_lock_shared` をサポートします。

- `lock_shared` メソッドは、スレッドがミューテックスの共有所有権を取得するまでそのスレッドの呼び出しをブロックします。

- `unlock_shared` メソッドは、スレッドの呼び出しによって保持されるミューテックスの共有所有権を解放します。

- `try_lock_shared` メソッドは、ミューテックスをブロックせずに共有所有権を取得しようとします。 その戻り値の型は、`bool` に変換でき、メソッドが所有権を得ると `true` になりますが、それ以外の場合は `false` です。

クラス `shared_timed_mutex` は、*共有 timed mutex 型*、つまり、共有 mutex 型と timed mutex 型の両方の要件を満たす型です。

共有 timed mutex 型は、追加のメソッド `try_lock_shared_for` および `try_lock_shared_until` をサポートします。

- `try_lock_shared_for` メソッドは、パラメーターで指定した期間が経過するまで、ミューテックスの共有所有権を取得しようとします。 この期間が正ではない場合、このメソッドは `try_lock_shared` と等しくなります。 このメソッドは、共有所有権を取得しない限り、指定した期間内では返しません。 その戻り値は、メソッドが所有権を取得した場合は `true`、それ以外の場合は `false` です。

- `try_lock_shared_until` メソッドは、指定された絶対時間が経過するまで、ミューテックスの共有所有権を取得しようとします。 指定した時間が既に経過している場合、このメソッドは `try_lock_shared` と等しくなります。 このメソッドは、共有所有権を取得しない限り、指定した時間の前に返しません。 その戻り値は、メソッドが所有権を取得した場合は `true`、それ以外の場合は `false` です。

`shared_lock` テンプレート クラスは時間指定のロックのサポートおよび共有ミューテックスへの所有権の転送のサポートを拡張します。 ミューテックスの所有権は構築時または構築後に取得でき、別の `shared_lock` オブジェクトに転送できます。 `shared_lock` 型のオブジェクトは移動できますが、コピーできません。

> [!WARNING]
> Visual Studio 2015 以降では、C++ 標準ライブラリの同期型は Windows 同期プリミティブに基づいており、不要になった (ターゲット プラットフォームが Windows XP の場合) を除く ConcRT を使用します。 定義された型&lt;shared_mutex > は、ConcRT 型または関数では使用できません。

## <a name="classes"></a>クラス

###  <a name="class_shared_mutex"></a> shared_mutex クラス

クラス `shared_mutex` は、共有所有権セマンティクスで非再帰的なミューテックスを実装します。

```cpp
class shared_mutex {
public:
   shared_mutex();
   ~shared_mutex();
   shared_mutex(const shared_mutex&) = delete;
   shared_mutex& operator=(const shared_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   void unlock_shared();
   // Getters
   typedef void** native_handle_type; // implementation defined
   native_handle_type native_handle();
   };
```

###  <a name="class_shared_timed_mutex"></a> shared_timed_mutex クラス

クラス `shared_timed_mutex` は、timed mutex 型の要件を満たしている共有所有権セマンティクスで非再帰的なミューテックスを実装します。

```cpp
class shared_timed_mutex {
public:
   shared_timed_mutex();
   ~shared_timed_mutex();
   shared_timed_mutex(const shared_timed_mutex&) = delete;
   shared_timed_mutex& operator=(const shared_timed_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   template <class Rep, class Period>
   bool try_lock_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   template <class Rep, class Period>
   bool try_lock_shared_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_shared_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock_shared();
   };
```

###  <a name="&lt;shared"></a> shared_lock クラス

テンプレート クラス `shared_lock` は、スコープ内の共有ミューテックス オブジェクトの共有所有権を制御します。 テンプレート パラメーターは、共有 mutex 型である必要があります。

```cpp
class shared_lock {
public:
   typedef Mutex mutex_type;
   shared_lock() noexcept;
   explicit shared_lock(mutex_type& m);
   // blocking
   shared_lock(mutex_type& m, defer_lock_t) noexcept;
   shared_lock(mutex_type& m, try_to_lock_t);
   shared_lock(mutex_type& m, adopt_lock_t);
   template <class Clock, class Duration>
   shared_lock(mutex_type& m,
   const chrono::time_point<Clock, Duration>& abs_time);
   template <class Rep, class Period>
   shared_lock(mutex_type& m,
   const chrono::duration<Rep, Period>& rel_time);
   ~shared_lock();
   shared_lock(shared_lock const&) = delete;
   shared_lock& operator=(shared_lock const&) = delete;
   shared_lock(shared_lock&& u) noexcept;
   shared_lock& operator=(shared_lock&& u) noexcept;
   void lock();
   // blocking
   bool try_lock();
   template <class Rep, class Period>
   bool try_lock_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock();
   // Setters
   void swap(shared_lock& u) noexcept;
   mutex_type* release() noexcept;
   // Getters
   bool owns_lock() const noexcept;
   explicit operator bool () const noexcept;
   mutex_type* mutex() const noexcept;
private:
   mutex_type* pm; // exposition only
   bool owns; // exposition only
   };
```

## <a name="functions"></a>関数

###  <a name="function_swap"></a> スワップ

`shared_lock` オブジェクトを交換します。

```cpp
template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
```

2 つの `shared_lock` オブジェクトの内容を交換します。 実質的に `x.swap(y)` と同じです。

## <a name="requirements"></a>要件

**ヘッダー:** &lt;shared_mutex>

**名前空間:** std

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)
[&lt;ミュー テックス >](../standard-library/mutex.md)
