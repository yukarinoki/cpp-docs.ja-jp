---
title: lock クラス
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::lock::lock
- msclr::lock::is_locked
- msclr::lock.is_locked
- msclr::lock::acquire
- msclr::lock::try_acquire
- msclr::lock::release
- msclr::lock::operator==
- msclr::lock::operator!=
helpviewer_keywords:
- msclr::lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
ms.openlocfilehash: b2ae1be31233e55aa34d6f3046d90fb2127348c0
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "80080040"
---
# <a name="lock-class"></a>lock クラス

このクラスは、複数のスレッドからオブジェクトへのアクセスを同期するためのロックの取得を自動化します。  構築時にロックが取得され、破棄されるとロックが解放されます。

## <a name="syntax"></a>構文

```cpp
ref class lock;
```

## <a name="remarks"></a>解説

`lock` は CLR オブジェクトでのみ使用でき、CLR コードでのみ使用できます。

内部的には、ロッククラスは <xref:System.Threading.Monitor> を使用してアクセスを同期します。 詳細については、参照されている記事を参照してください。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|Name|Description|
|---------|-----------|
|[lock::lock](#lock)|`lock` オブジェクトを構築し、必要に応じて、ロックの取得を無期限に、指定した時間だけ待機するか、まったく使用しないかを待機します。|
|[lock::~lock](#tilde-lock)|`lock` オブジェクトを Destructs します。|

### <a name="public-methods"></a>パブリック メソッド

|Name|Description|
|---------|-----------|
|[lock::acquire](#acquire)|オブジェクトのロックを取得します。また、必要に応じて、ロックの取得を無期限に、指定した時間だけ待機するか、まったく使用しないかを待機します。|
|[lock::is_locked](#is-locked)|ロックが保持されているかどうかを示します。|
|[lock::release](#release)|ロックを解放します。|
|[lock::try_acquire](#try-acquire)|オブジェクトのロックを取得し、指定された時間待機し、例外をスローするのではなく、取得の成功を報告するために `bool` を返します。|

### <a name="public-operators"></a>パブリック演算子

|Name|Description|
|---------|-----------|
|[lock:: operator&nbsp;bool](#operator-bool)|条件式で `lock` を使用するための演算子。|
|[lock::operator==](#operator-equality)|等値演算子。|
|[lock::operator!=](#operator-inequality)|非等値演算子。|

## <a name="requirements"></a>必要条件

**ヘッダーファイル**\<msclr\ >

**名前空間**msclr

## <a name="locklock"></a><a name="lock"></a>lock:: lock

`lock` オブジェクトを構築し、必要に応じて、ロックの取得を無期限に、指定した時間だけ待機するか、まったく使用しないかを待機します。

```cpp
template<class T> lock(
   T ^ _object
);
template<class T> lock(
   T ^ _object,
   int _timeout
);
template<class T> lock(
   T ^ _object,
   System::TimeSpan _timeout
);
template<class T> lock(
   T ^ _object,
   lock_later
);
```

### <a name="parameters"></a>パラメーター

*_object*<br/>
ロックされるオブジェクト。

*_timeout*<br/>
タイムアウト値 (ミリ秒単位) または <xref:System.TimeSpan>。

### <a name="exceptions"></a>例外

タイムアウト前にロックの取得が行われない場合は、<xref:System.ApplicationException> をスローします。

### <a name="remarks"></a>解説

コンストラクターの最初の3つの形式は、指定されたタイムアウト期間内 (または、何も指定されていない場合は <xref:System.Threading.Timeout.Infinite>) に `_object` のロックを取得しようとします。

コンストラクターの4番目の形式は、`_object`でロックを取得しません。 `lock_later` は[lock_when 列挙型](../dotnet/lock-when-enum.md)のメンバーです。 Lock [:: 獲得](../dotnet/lock-acquire.md)または[lock:: try_acquire](../dotnet/lock-try-acquire.md)を使用して、この場合にロックを取得します。

このロックは、デストラクターが呼び出されたときに自動的に解放されます。

`_object` を <xref:System.Threading.ReaderWriterLock>することはできません。  そのような場合は、コンパイラエラーが発生します。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの1つのインスタンスを使用します。 クラスは、自身のロックを使用して、内部データへのアクセスがスレッドごとに一貫していることを確認します。 メインアプリケーションスレッドは、クラスの同じインスタンスでロックを使用して、ワーカースレッドがまだ存在するかどうかを定期的にチェックします。 メインアプリケーションは、すべてのワーカースレッドがタスクを完了するまで、終了を待機します。

```cpp
// msl_lock_lock.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="locklock"></a><a name="tilde-lock"></a>lock:: ~ lock

`lock` オブジェクトを Destructs します。

```cpp
~lock();
```

### <a name="remarks"></a>解説

デストラクターは[lock:: release](../dotnet/lock-release.md)を呼び出します。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの1つのインスタンスを使用します。  クラスは、自身のロックを使用して、内部データへのアクセスがスレッドごとに一貫していることを確認します。  メインアプリケーションスレッドは、クラスの同じインスタンスでロックを使用して、ワーカースレッドがまだ存在するかどうかを定期的にチェックします。 メインアプリケーションは、すべてのワーカースレッドがタスクを完了するまで、終了を待機します。

```cpp
// msl_lock_dtor.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockacquire"></a><a name="acquire"></a>lock:: 獲得

オブジェクトのロックを取得します。また、必要に応じて、ロックの取得を無期限に、指定した時間だけ待機するか、まったく使用しないかを待機します。

```cpp
void acquire();
void acquire(
   int _timeout
);
void acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>パラメーター

*_timeout*<br/>
タイムアウト値 (ミリ秒単位) または <xref:System.TimeSpan>。

### <a name="exceptions"></a>例外

タイムアウト前にロックの取得が行われない場合は、<xref:System.ApplicationException> をスローします。

### <a name="remarks"></a>解説

タイムアウト値が指定されていない場合、既定のタイムアウトは <xref:System.Threading.Timeout.Infinite>になります。

ロックが既に取得されている場合、この関数は何も行いません。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの1つのインスタンスを使用します。  クラスは、自身のロックを使用して、内部データへのアクセスがスレッドごとに一貫していることを確認します。 メインアプリケーションスレッドは、クラスの同じインスタンスでロックを使用して、ワーカースレッドがまだ存在するかどうかを定期的にチェックします。 メインアプリケーションは、すべてのワーカースレッドがタスクを完了するまで、終了を待機します。

```cpp
// msl_lock_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockis_locked"></a><a name="is-locked"></a>lock:: is_locked

ロックが保持されているかどうかを示します。

```cpp
bool is_locked();
```

### <a name="return-value"></a>戻り値

ロックが保持されている場合は `true`。それ以外の場合は `false`。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの1つのインスタンスを使用します。  クラスは、自身のロックを使用して、内部データへのアクセスがスレッドごとに一貫していることを確認します。  メインアプリケーションスレッドは、クラスの同じインスタンスでロックを使用して、ワーカースレッドがまだ存在するかどうかを定期的にチェックし、すべてのワーカースレッドがそのタスクを完了するまで、終了を待機します。

```cpp
// msl_lock_is_locked.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l.is_locked()) { // check if we got the lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockoperator-bool"></a><a name="operator-bool"></a>lock:: operator bool

条件式で `lock` を使用するための演算子。

```cpp
operator bool();
```

### <a name="return-value"></a>戻り値

ロックが保持されている場合は `true`。それ以外の場合は `false`。

### <a name="remarks"></a>解説

この演算子は、実際には、整数型に変換できないため、`bool` よりも安全な `_detail_class::_safe_bool` に変換されます。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの1つのインスタンスを使用します。  クラスは、自身のロックを使用して、内部データへのアクセスがスレッドごとに一貫していることを確認します。 メインアプリケーションスレッドは、クラスの同じインスタンスでロックを使用して、ワーカースレッドがまだ存在するかどうかを定期的にチェックします。 メインアプリケーションは、すべてのワーカースレッドがタスクを完了するまで、終了を待機します。

```cpp
// msl_lock_op_bool.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      l.try_acquire(50); // try to acquire lock, don't throw an exception if can't
      if (l) { // use bool operator to check for lock
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockrelease"></a><a name="release"></a>lock:: release

ロックを解放します。

```cpp
void release();
```

### <a name="remarks"></a>解説

ロックが保持されていない場合、`release` は何も行いません。

この関数を明示的に呼び出す必要はありません。 `lock` オブジェクトがスコープ外に出ると、そのデストラクターは `release`を呼び出します。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの1つのインスタンスを使用します。 クラスは、自身のロックを使用して、内部データへのアクセスがスレッドごとに一貫していることを確認します。 メインアプリケーションスレッドは、クラスの同じインスタンスでロックを使用して、ワーカースレッドがまだ存在するかどうかを定期的にチェックします。 メインアプリケーションは、すべてのワーカースレッドがタスクを完了するまで、終了を待機します。

```cpp
// msl_lock_release.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="locktry_acquire"></a><a name="try-acquire"></a>lock:: try_acquire

オブジェクトのロックを取得し、指定された時間待機し、例外をスローするのではなく、取得の成功を報告するために `bool` を返します。

```cpp
bool try_acquire(
   int _timeout_ms
);
bool try_acquire(
   System::TimeSpan _timeout
);
```

### <a name="parameters"></a>パラメーター

*_timeout*<br/>
タイムアウト値 (ミリ秒単位) または <xref:System.TimeSpan>。

### <a name="return-value"></a>戻り値

ロックが取得された場合は `true`。それ以外の場合は `false`。

### <a name="remarks"></a>解説

ロックが既に取得されている場合、この関数は何も行いません。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの1つのインスタンスを使用します。 クラスは、自身のロックを使用して、内部データへのアクセスがスレッドごとに一貫していることを確認します。 メインアプリケーションスレッドは、クラスの同じインスタンスでロックを使用して、ワーカースレッドがまだ存在するかどうかを定期的にチェックします。 メインアプリケーションは、すべてのワーカースレッドがタスクを完了するまで、終了を待機します。

```cpp
// msl_lock_try_acquire.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

ref class CounterClass {
private:
   int Counter;

public:
   property int ThreadCount;

   // function called by multiple threads, use lock to keep Counter consistent
   // for each thread
   void UseCounter() {
      try {
         lock l(this); // wait infinitely

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         for (int i = 0; i < 10; i++) {
            Counter++;
            Thread::Sleep(10);
         }

         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,
            Counter);

         Counter = 0;
         // lock is automatically released when it goes out of scope and its destructor is called
      }
      catch (...) {
         Console::WriteLine("Couldn't acquire lock!");
      }

      ThreadCount--;
   }
};

int main() {
   // create a few threads to contend for access to the shared data
   CounterClass^ cc = gcnew CounterClass;
   array<Thread^>^ tarr = gcnew array<Thread^>(5);
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);
   for (int i = 0; i < tarr->Length; i++) {
      tarr[i] = gcnew Thread(startDelegate);
      cc->ThreadCount++;
      tarr[i]->Start();
   }

   // keep our main thread alive until all worker threads have completed
   lock l(cc, lock_later); // don't lock now, just create the object
   while (true) {
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't
         if (0 == cc->ThreadCount) {
            Console::WriteLine("All threads completed.");
            break; // all threads are gone, exit while
         }
         else {
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);
            l.release(); // some threads exist, let them do their work
         }
      }
   }
}
```

```Output
In thread 3, Counter = 0
In thread 3, Counter = 10
In thread 5, Counter = 0
In thread 5, Counter = 10
In thread 7, Counter = 0
In thread 7, Counter = 10
In thread 4, Counter = 0
In thread 4, Counter = 10
In thread 6, Counter = 0
In thread 6, Counter = 10
All threads completed.
```

## <a name="lockoperator"></a><a name="operator-equality"></a>lock:: operator = =

等値演算子。

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>パラメーター

*t*<br/>
等しいかどうかを比較するオブジェクト。

### <a name="return-value"></a>戻り値

`t` がロックのオブジェクトと同じ場合は `true` を返します。それ以外の場合は `false` を返します。

### <a name="example"></a>例

```cpp
// msl_lock_op_eq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   lock l1(o1);
   if (l1 == o1) {
      Console::WriteLine("Equal!");
   }
}
```

```Output
Equal!
```

## <a name="lockoperator"></a><a name="operator-inequality"></a>lock:: operator! =

非等値演算子。

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>パラメーター

*t*<br/>
等しくないかどうかを比較するオブジェクト。

### <a name="return-value"></a>戻り値

`t` がロックのオブジェクトと異なる場合は `true` を返します。それ以外の場合は `false` を返します。

### <a name="example"></a>例

```cpp
// msl_lock_op_ineq.cpp
// compile with: /clr
#include <msclr/lock.h>

using namespace System;
using namespace System::Threading;
using namespace msclr;

int main () {
   Object^ o1 = gcnew Object;
   Object^ o2 = gcnew Object;
   lock l1(o1);
   if (l1 != o2) {
      Console::WriteLine("Inequal!");
   }
}
```

```Output
Inequal!
```