---
title: A.16 ロックの使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 873bf32b-6cfe-4ce1-b994-bef80b50f399
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2bb901ab311221f1375bb5f3bfe7f996981e97a6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432751"
---
# <a name="a16---using-locks"></a>A.16 ロックの使用

次の例では、(の[セクション 3.2](../../parallel/openmp/3-2-lock-functions.md) 41 ページの) ロック関数の引数は型である必要がありますに注意してください`omp_lock_t`、フラッシュされる前にする必要がないとします。  ロック関数では、最初の重要なセクションにエントリを待つ間アイドル状態であるが、2 番目のエントリの待機中に他の作業を行うスレッドをによりします。  `omp_set_lock`関数のブロックが、`omp_test_lock`関数は、作業を行う skip() で許可していません。

## <a name="example"></a>例

### <a name="code"></a>コード

```
// omp_using_locks.c
// compile with: /openmp /c
#include <stdio.h>
#include <omp.h>

void work(int);
void skip(int);

int main() {
   omp_lock_t lck;
   int id;

   omp_init_lock(&lck);
   #pragma omp parallel shared(lck) private(id)
   {
      id = omp_get_thread_num();

      omp_set_lock(&lck);
      printf_s("My thread id is %d.\n", id);

      // only one thread at a time can execute this printf
      omp_unset_lock(&lck);

      while (! omp_test_lock(&lck)) {
         skip(id);   // we do not yet have the lock,
                     // so we must do something else
      }
      work(id);     // we now have the lock
                    // and can do the work
      omp_unset_lock(&lck);
   }
   omp_destroy_lock(&lck);
}
```