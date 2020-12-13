---
description: '詳細情報: lock_when 列挙型'
title: lock_when Enum
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msclr::lock_when
- msclr.lock_when
- lock_when
helpviewer_keywords:
- lock_when enum
ms.assetid: 6b87bbe9-63cd-450d-a02e-bb91ffd0dcea
ms.openlocfilehash: 5fcc0e428056f5076803ec1ba82bb20207e37189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344485"
---
# <a name="lock_when-enum"></a>lock_when Enum

遅延ロックを指定します。

## <a name="syntax"></a>構文

```
enum lock_when {
   lock_later
};
```

## <a name="remarks"></a>解説

Lock [:: lock](./lock-class.md#lock)に渡されると、ロックを取得しないように `lock_later` 指定します。

## <a name="example"></a>例

この例では、クラスの1つのインスタンスを複数のスレッドにわたって使用します。  クラスは、自身のロックを使用して、内部データへのアクセスがスレッドごとに一貫していることを確認します。  メインアプリケーションスレッドは、クラスの同じインスタンスでロックを使用して、ワーカースレッドがまだ存在するかどうかを定期的にチェックし、すべてのワーカースレッドがそのタスクを完了するまで、終了を待機します。

```cpp
// msl_lock_lock_when.cpp
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

## <a name="requirements"></a>要件

**ヘッダー ファイル** \<msclr\lock.h>

**名前空間** msclr

## <a name="see-also"></a>関連項目

[lock](../dotnet/lock.md)
