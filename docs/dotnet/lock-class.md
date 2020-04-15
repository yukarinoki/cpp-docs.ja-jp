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
ms.openlocfilehash: ea09dd3d4a2eaf4cf7708d09509cfecfa4a6c6d5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373077"
---
# <a name="lock-class"></a>lock クラス

このクラスは、複数のスレッドからオブジェクトへのアクセスを同期するためのロックの取得を自動化します。  構築されると、ロックを取得し、破棄されるとロックを解放します。

## <a name="syntax"></a>構文

```cpp
ref class lock;
```

## <a name="remarks"></a>解説

`lock`は CLR オブジェクトでのみ使用でき、CLR コードでのみ使用できます。

内部的には、ロック クラスは<xref:System.Threading.Monitor>アクセスの同期に使用します。 詳細については、参照先の記事を参照してください。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|---------|-----------|
|[ロック::ロック](#lock)|ロックを`lock`永遠に取得するのを待機するオブジェクトを、指定した時間だけ、またはまったく行わないオブジェクトを構築します。|
|[lock::~lock](#tilde-lock)|オブジェクトを`lock`破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|---------|-----------|
|[lock::acquire](#acquire)|オブジェクトのロックを取得し、オプションでロックを永遠に取得するのを待機するか、指定した時間だけ、またはまったくロックを取得しない。|
|[lock::is_locked](#is-locked)|ロックが保持されているかどうかを示します。|
|[lock::release](#release)|ロックを解除します。|
|[lock::try_acquire](#try-acquire)|オブジェクトのロックを取得し、指定された時間待機し、例外をスローする代`bool`わりに取得の成功を報告するためにを返します。|

### <a name="public-operators"></a>公共事業者

|名前|説明|
|---------|-----------|
|[ロック::オペレータ&nbsp;ブール](#operator-bool)|条件式で`lock`使用する演算子。|
|[lock::operator==](#operator-equality)|等値演算子。|
|[ロック::演算子!=](#operator-inequality)|不等式演算子。|

## <a name="requirements"></a>必要条件

**ヘッダー ファイル**\<msclr\lock.h>

**名前空間**msclr

## <a name="locklock"></a><a name="lock"></a>ロック::ロック

ロックを`lock`永遠に取得するのを待機するオブジェクトを、指定した時間だけ、またはまったく行わないオブジェクトを構築します。

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
ロックするオブジェクト。

*_timeout*<br/>
タイムアウト値 (ミリ秒単位または<xref:System.TimeSpan>.

### <a name="exceptions"></a>例外

タイムアウト前<xref:System.ApplicationException>にロック取得が発生しない場合にスローします。

### <a name="remarks"></a>解説

コンストラクタの最初の 3 つの形式は、指定された`_object`タイムアウト期間内 (または<xref:System.Threading.Timeout.Infinite>指定されていない場合) にロックを取得しようとします。

コンストラクタの 4 番目の形式では、 のロック`_object`は取得されません。 `lock_later`は[、lock_when列挙型](../dotnet/lock-when-enum.md)のメンバーです。 この場合、ロックを取得するには[lock::acquire](../dotnet/lock-acquire.md)または[lock::try_acquire](../dotnet/lock-try-acquire.md)を使用します。

デストラクターが呼び出されると、ロックは自動的に解放されます。

`_object`はできません<xref:System.Threading.ReaderWriterLock>。  コンパイル エラーが発生した場合は、エラーが発生します。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの単一インスタンスを使用します。 クラスは、自身のロックを使用して、内部データへのアクセスが各スレッドに対して一貫していることを確認します。 メイン アプリケーション スレッドは、クラスの同じインスタンスのロックを使用して、ワーカー スレッドがまだ存在するかどうか定期的に確認します。 メイン アプリケーションは、すべてのワーカー スレッドがタスクを完了するまで終了するまで待機します。

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

## <a name="locklock"></a><a name="tilde-lock"></a>ロック::~ロック

オブジェクトを`lock`破棄します。

```cpp
~lock();
```

### <a name="remarks"></a>解説

デストラクターは[lock::release](../dotnet/lock-release.md)を呼び出します。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの単一インスタンスを使用します。  クラスは、自身のロックを使用して、内部データへのアクセスが各スレッドに対して一貫していることを確認します。  メイン アプリケーション スレッドは、クラスの同じインスタンスのロックを使用して、ワーカー スレッドがまだ存在するかどうか定期的に確認します。 メイン アプリケーションは、すべてのワーカー スレッドがタスクを完了するまで終了するまで待機します。

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

## <a name="lockacquire"></a><a name="acquire"></a>ロック::取得

オブジェクトのロックを取得し、オプションでロックを永遠に取得するのを待機するか、指定した時間だけ、またはまったくロックを取得しない。

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
タイムアウト値 (ミリ秒単位または<xref:System.TimeSpan>)。

### <a name="exceptions"></a>例外

タイムアウト前<xref:System.ApplicationException>にロック取得が発生しない場合にスローします。

### <a name="remarks"></a>解説

タイムアウト値が指定されていない場合、デフォルトのタイムアウトは<xref:System.Threading.Timeout.Infinite>です。

ロックがすでに取得されている場合、この関数は何も実行しません。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの単一インスタンスを使用します。  クラスは、自身のロックを使用して、内部データへのアクセスが各スレッドに対して一貫していることを確認します。 メイン アプリケーション スレッドは、クラスの同じインスタンスのロックを使用して、ワーカー スレッドがまだ存在するかどうか定期的に確認します。 メイン アプリケーションは、すべてのワーカー スレッドがタスクを完了するまで終了するまで待機します。

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

## <a name="lockis_locked"></a><a name="is-locked"></a>ロック::is_locked

ロックが保持されているかどうかを示します。

```cpp
bool is_locked();
```

### <a name="return-value"></a>戻り値

`true`ロックが保持されている場合、`false`それ以外の場合。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの単一インスタンスを使用します。  クラスは、自身のロックを使用して、内部データへのアクセスが各スレッドに対して一貫していることを確認します。  メイン アプリケーション スレッドは、クラスの同じインスタンスのロックを使用して、ワーカー スレッドがまだ存在するかどうか定期的に確認し、すべてのワーカー スレッドがタスクを完了するまで終了するのを待機します。

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

## <a name="lockoperator-bool"></a><a name="operator-bool"></a>ロック::オペレータブール

条件式で`lock`使用する演算子。

```cpp
operator bool();
```

### <a name="return-value"></a>戻り値

`true`ロックが保持されている場合、`false`それ以外の場合。

### <a name="remarks"></a>解説

この演算子は、整数型`_detail_class::_safe_bool`に変換できないため、`bool`実際に変換する方が安全です。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの単一インスタンスを使用します。  クラスは、自身のロックを使用して、内部データへのアクセスが各スレッドに対して一貫していることを確認します。 メイン アプリケーション スレッドは、クラスの同じインスタンスのロックを使用して、ワーカー スレッドがまだ存在するかどうか定期的に確認します。 メイン アプリケーションは、すべてのワーカー スレッドがタスクを完了するまで終了するまで待機します。

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

## <a name="lockrelease"></a><a name="release"></a>ロック::リリース

ロックを解除します。

```cpp
void release();
```

### <a name="remarks"></a>解説

ロックが保持されていない場合は、`release`何もしません。

この関数を明示的に呼び出す必要はありません。 オブジェクトが`lock`スコープ外に出ると、そのデストラクターが`release`呼び出されます。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの単一インスタンスを使用します。 クラスは、自身のロックを使用して、内部データへのアクセスが各スレッドに対して一貫していることを確認します。 メイン アプリケーション スレッドは、クラスの同じインスタンスのロックを使用して、ワーカー スレッドがまだ存在するかどうか定期的に確認します。 メイン アプリケーションは、すべてのワーカー スレッドがタスクを完了するまで終了するまで待機します。

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

## <a name="locktry_acquire"></a><a name="try-acquire"></a>ロック::try_acquire

オブジェクトのロックを取得し、指定された時間待機し、例外をスローする代`bool`わりに取得の成功を報告するためにを返します。

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
タイムアウト値 (ミリ秒単位または<xref:System.TimeSpan>)。

### <a name="return-value"></a>戻り値

`true`ロックが取得された場合`false`、それ以外の場合。

### <a name="remarks"></a>解説

ロックがすでに取得されている場合、この関数は何も実行しません。

### <a name="example"></a>例

この例では、複数のスレッドでクラスの単一インスタンスを使用します。 クラスは、自身のロックを使用して、内部データへのアクセスが各スレッドに対して一貫していることを確認します。 メイン アプリケーション スレッドは、クラスの同じインスタンスのロックを使用して、ワーカー スレッドがまだ存在するかどうか定期的に確認します。 メイン アプリケーションは、すべてのワーカー スレッドがタスクを完了するまで終了するまで待機します。

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

## <a name="lockoperator"></a><a name="operator-equality"></a>ロック::演算子==

等値演算子。

```cpp
template<class T> bool operator==(
   T t
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
等しいかどうかを比較するオブジェクト。

### <a name="return-value"></a>戻り値

ロックのオブジェクトと同じかどうかを`true``t`返します。 `false`

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

## <a name="lockoperator"></a><a name="operator-inequality"></a>ロック::演算子!=

不等式演算子。

```cpp
template<class T> bool operator!=(
   T t
);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
不等式を比較するオブジェクト。

### <a name="return-value"></a>戻り値

ロックのオブジェクトと異なるかどうかを`true``t`返します。 `false`

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
