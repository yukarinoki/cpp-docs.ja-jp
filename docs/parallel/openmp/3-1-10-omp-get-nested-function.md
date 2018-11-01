---
title: 3.1.10 omp_get_nested 関数
ms.date: 11/04/2016
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
ms.openlocfilehash: a4db1e21f344f5cc58e2027b0816f9c8fb40b3bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519922"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested 関数

`omp_get_nested`関数 0 を返します 0 以外の値を使用している場合、入れ子になった並列処理が有効になっている場合は無効になります。 入れ子になった並列処理の詳細については、40 ページの 3.1.9 セクションを参照してください。 形式は次のとおりです。

```
#include <omp.h>
int omp_get_nested(void);
```

実装が入れ子になった並列処理を実装していない場合、この関数は常に 0 を返します。