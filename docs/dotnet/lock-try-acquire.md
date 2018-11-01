---
title: lock::try_acquire
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- try_acquire
- lock.try_acquire
- msclr.lock.try_acquire
- lock::try_acquire
- msclr::lock::try_acquire
helpviewer_keywords:
- lock::try_acquire
ms.assetid: ef0649a9-e611-4495-84bd-2784533221d9
ms.openlocfilehash: ea16a495931c094a0088653bd0db9accca4bb486
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440951"
---
# <a name="locktryacquire"></a>lock::try_acquire

一定の時間を待機していると、返すオブジェクトのロックを取得、`bool`例外をスローする代わりに取得の成功を報告します。

## <a name="syntax"></a>構文

```
bool try_acquire(
   int _timeout_ms
);
bool try_acquire(
   System::TimeSpan _timeout
);
```

#### <a name="parameters"></a>パラメーター

*タイムアウト _t*<br/>
タイムアウト値 (ミリ秒単位) またはとして、<xref:System.TimeSpan>します。

## <a name="return-value"></a>戻り値

**true**ロックが取得された場合**false**それ以外の場合。

## <a name="remarks"></a>Remarks

場合は、ロックは既に取得されて、何もされません。

## <a name="example"></a>例

この例では、複数のスレッド クラスの 1 つのインスタンスを使用します。  クラスでは、その内部データへのアクセスがスレッドごとに一貫性のあることを確認するのに自体に対するロックを使用します。  メイン アプリケーション スレッドは、すべてのワーカー スレッドがまだ存在していて、そのタスクが完了するまでのすべてのワーカー スレッドの終了を待機を定期的に確認するクラスの同じインスタンスでロックを使用します。

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

## <a name="requirements"></a>必要条件

**ヘッダー ファイル** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>関連項目

[lock のメンバー](../dotnet/lock-members.md)<br/>
[lock::acquire](../dotnet/lock-acquire.md)