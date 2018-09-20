---
title: (OpenMP) の |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- for
dev_langs:
- C++
helpviewer_keywords:
- for OpenMP directive
ms.assetid: 8b54e034-9db2-4c1a-a2b1-72e14e930506
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fea7679e8e2d27db8f8f4ff4087bae6ebc84ab1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439550"
---
# <a name="for-openmp"></a>for (OpenMP)

行われる動作、スレッド間で除算する、並行領域内の for ループします。

## <a name="syntax"></a>構文

```
#pragma omp [parallel] for [clauses]
   for_statement
```

## <a name="arguments"></a>引数

*句*<br/>
(省略可能)0 個以上の句。 サポートされている句の一覧については、「解説」を参照してください。**の**します。

*for_statement*<br/>
For ループします。 ユーザー コードで未定義の動作が発生、ループ インデックス変数を変更します。

## <a name="remarks"></a>Remarks

**の**ディレクティブは、次の OpenMP 句をサポートしています。

- [firstprivate](../../../parallel/openmp/reference/firstprivate.md)

- [lastprivate](../../../parallel/openmp/reference/lastprivate.md)

- [nowait](../../../parallel/openmp/reference/nowait.md)

- [順序付け](../../../parallel/openmp/reference/ordered-openmp-directives.md)

- [private](../../../parallel/openmp/reference/private-openmp.md)

- [reduction](../../../parallel/openmp/reference/reduction.md)

- [schedule](../../../parallel/openmp/reference/schedule.md)

場合**並列**が指定されても、`clause`句受け入れ可能で、**並列**または**の**ディレクティブを除く**nowait**.

詳細については、次を参照してください。 [2.4.1 for のコンストラクト](../../../parallel/openmp/2-4-1-for-construct.md)します。

## <a name="example"></a>例

```
// omp_for.cpp
// compile with: /openmp
#include <stdio.h>
#include <math.h>
#include <omp.h>

#define NUM_THREADS 4
#define NUM_START 1
#define NUM_END 10

int main() {
   int i, nRet = 0, nSum = 0, nStart = NUM_START, nEnd = NUM_END;
   int nThreads = 0, nTmp = nStart + nEnd;
   unsigned uTmp = (unsigned((abs(nStart - nEnd) + 1)) *
                               unsigned(abs(nTmp))) / 2;
   int nSumCalc = uTmp;

   if (nTmp < 0)
      nSumCalc = -nSumCalc;

   omp_set_num_threads(NUM_THREADS);

   #pragma omp parallel default(none) private(i) shared(nSum, nThreads, nStart, nEnd)
   {
      #pragma omp master
      nThreads = omp_get_num_threads();

      #pragma omp for
      for (i=nStart; i<=nEnd; ++i) {
            #pragma omp atomic
            nSum += i;
      }
   }

   if  (nThreads == NUM_THREADS) {
      printf_s("%d OpenMP threads were used.\n", NUM_THREADS);
      nRet = 0;
   }
   else {
      printf_s("Expected %d OpenMP threads, but %d were used.\n",
               NUM_THREADS, nThreads);
      nRet = 1;
   }

   if (nSum != nSumCalc) {
      printf_s("The sum of %d through %d should be %d, "
               "but %d was reported!\n",
               NUM_START, NUM_END, nSumCalc, nSum);
      nRet = 1;
   }
   else
      printf_s("The sum of %d through %d is %d\n",
               NUM_START, NUM_END, nSum);
}
```

```Output
4 OpenMP threads were used.
The sum of 1 through 10 is 55
```

## <a name="see-also"></a>関連項目

[ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)