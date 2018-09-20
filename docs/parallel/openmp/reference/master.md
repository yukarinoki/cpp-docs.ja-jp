---
title: マスター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- master
dev_langs:
- C++
helpviewer_keywords:
- master OpenMP directive
ms.assetid: 559ed974-e02a-486e-a23f-31556429b2c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9472854e22b1a1f7c4a13316244554b473f48298
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423729"
---
# <a name="master"></a>master

マスター スレッドのみが、プログラムのセクションを実行することを指定します。

## <a name="syntax"></a>構文

```
#pragma omp master
{
   code_block
}
```

## <a name="remarks"></a>Remarks

**マスター**ディレクティブに OpenMP 句がサポートされていません。

[単一](../../../parallel/openmp/reference/single.md)ディレクティブを使用して、シングル スレッドでコードのセクションを実行するように指定できます。

詳細については、次を参照してください。 [2.6.1 master コンストラクト](../../../parallel/openmp/2-6-1-master-construct.md)します。

## <a name="example"></a>例

```
// omp_master.cpp
// compile with: /openmp
#include <omp.h>
#include <stdio.h>

int main( )
{
    int a[5], i;

    #pragma omp parallel
    {
        // Perform some computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] = i * i;

        // Print intermediate results.
        #pragma omp master
            for (i = 0; i < 5; i++)
                printf_s("a[%d] = %d\n", i, a[i]);

        // Wait.
        #pragma omp barrier

        // Continue with the computation.
        #pragma omp for
        for (i = 0; i < 5; i++)
            a[i] += i;
    }
}
```

```Output
a[0] = 0
a[1] = 1
a[2] = 4
a[3] = 9
a[4] = 16
```

## <a name="see-also"></a>関連項目

[ディレクティブ](../../../parallel/openmp/reference/openmp-directives.md)