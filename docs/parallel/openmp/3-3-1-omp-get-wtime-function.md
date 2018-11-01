---
title: 3.3.1 omp_get_wtime 関数
ms.date: 11/04/2016
ms.assetid: 90188bd2-c53e-4398-8946-d3ecc92fa0f6
ms.openlocfilehash: 544a1bc9a613a2888cb7c5e68e54fdfae1b1c333
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460568"
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