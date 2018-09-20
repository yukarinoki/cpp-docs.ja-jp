---
title: omp_get_wtime |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
f1_keywords:
- omp_get_wtime
dev_langs:
- C++
helpviewer_keywords:
- omp_get_wtime OpenMP function
ms.assetid: c8dee105-ec1b-42e5-a6e3-edeedcf9854c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f2d02bf5b8de0094a18d456a569b24fed2e03b8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391762"
---
# <a name="ompgetwtime"></a>omp_get_wtime

ある時点から経過した時間の秒の値を返します。

## <a name="syntax"></a>構文

```
double omp_get_wtime( );
```

## <a name="return-value"></a>戻り値

いくつか任意が一貫性のあるポイントからの経過時間の秒数値を返します。

## <a name="remarks"></a>Remarks

そのポイントは、後続の比較ができるようにするプログラムの実行中に一貫性のある残ります。

詳細については、次を参照してください。 [3.3.1 omp_get_wtime 関数](../../../parallel/openmp/3-3-1-omp-get-wtime-function.md)します。

## <a name="example"></a>例

```
// omp_get_wtime.cpp
// compile with: /openmp
#include "omp.h"
#include <stdio.h>
#include <windows.h>

int main() {
    double start = omp_get_wtime( );
    Sleep(1000);
    double end = omp_get_wtime( );
    double wtick = omp_get_wtick( );

    printf_s("start = %.16g\nend = %.16g\ndiff = %.16g\n",
             start, end, end - start);

    printf_s("wtick = %.16g\n1/wtick = %.16g\n",
             wtick, 1.0 / wtick);
}
```

```Output
start = 594255.3671159324
end = 594256.3664474116
diff = 0.9993314791936427
wtick = 2.793651148400146e-007
1/wtick = 3579545
```

## <a name="see-also"></a>関連項目

[関数](../../../parallel/openmp/reference/openmp-functions.md)