---
title: A.31 スレッド セーフなロック関数
ms.date: 11/04/2016
ms.assetid: 3ad89eb8-076c-405a-be5e-88d3d707a832
ms.openlocfilehash: ad0116dbb3491058e81fd271f4917f7eb7bff460
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50613591"
---
# <a name="a31---thread-safe-lock-functions"></a>A.31 スレッド セーフなロック関数

次の C++ の例を使用して、並列領域でロックの配列を初期化する方法を示します`omp_init_lock`([セクション 3.2.1](../../parallel/openmp/3-2-1-omp-init-lock-and-omp-init-nest-lock-functions.md) 42 ページ)。

## <a name="example"></a>例

### <a name="code"></a>コード

```
// A_13_omp_init_lock.cpp
// compile with: /openmp
#include <omp.h>

omp_lock_t *new_locks() {
   int i;
   omp_lock_t *lock = new omp_lock_t[1000];
   #pragma omp parallel for private(i)
   for (i = 0 ; i < 1000 ; i++)
      omp_init_lock(&lock[i]);

   return lock;
}

int main () {}
```