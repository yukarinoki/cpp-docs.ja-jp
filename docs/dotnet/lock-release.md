---
title: lock::release
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- lock.release
- msclr::lock::release
- lock::release
- msclr.lock.release
helpviewer_keywords:
- lock::release
ms.assetid: b73d48fc-cf98-4b78-b39d-813d4a12fa84
ms.openlocfilehash: 2fdb3ab6f261aa4752911a93d5f5ae0f5d637f44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650372"
---
# <a name="lockrelease"></a>lock::release

ロックを解放します。

## <a name="syntax"></a>構文

```
void release();
```

## <a name="remarks"></a>Remarks

ロックが保持されていない場合`release`何も行われません。

この関数を明示的に呼び出す必要はありません。ときに、`lock`オブジェクトが、そのデストラクターの呼び出しのスコープ外になる`release`します。

## <a name="example"></a>例

この例では、複数のスレッド クラスの 1 つのインスタンスを使用します。  クラスでは、その内部データへのアクセスがスレッドごとに一貫性のあることを確認するのに自体に対するロックを使用します。  メイン アプリケーション スレッドは、すべてのワーカー スレッドがまだ存在していて、そのタスクが完了するまでのすべてのワーカー スレッドの終了を待機を定期的に確認するクラスの同じインスタンスでロックを使用します。

```
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

## <a name="requirements"></a>必要条件

**ヘッダー ファイル** \<msclr\lock.h >

**Namespace** msclr

## <a name="see-also"></a>関連項目

[lock のメンバー](../dotnet/lock-members.md)<br/>
[lock::~lock](../dotnet/lock-tilde-lock.md)