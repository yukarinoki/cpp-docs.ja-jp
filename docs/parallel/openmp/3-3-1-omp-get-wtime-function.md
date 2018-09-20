---
title: 3.3.1 omp_get_wtime 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec022e9c7e27c848ef535481993dd18dc45f695
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46430774"
---
# <a name="331-ompgetwtime-function"></a>3.3.1 omp_get_wtime 関数

`omp_get_wtime` 「過去の時間」からの秒数で関数が経過したウォール クロック時間に等しいにある倍精度浮動小数点値を返します。  実際「の時間、過去に」は任意ですが、アプリケーション プログラムの実行中に変わらないことが保証されます。 形式は次のとおりです。

```
#include <omp.h>
double omp_get_wtime(void);
```

次の例に示すように、経過時間を測定する関数が使用されることが予想されます。

```
double start;
double end;
start = omp_get_wtime();
... work to be timed ...
end = omp_get_wtime();
printf_s("Work took %f sec. time.\n", end-start);
```

返される時間は、「スレッドごとの時間」を使用してアプリケーションに参加しているすべてのスレッド間でグローバルに一貫性がある必要がなくなりますするものでは。