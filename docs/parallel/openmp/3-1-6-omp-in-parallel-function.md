---
title: 3.1.6 omp_in_parallel 関数
ms.date: 11/04/2016
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
ms.openlocfilehash: 2f251cb994771278c7f4e3f50f01e02126f6f88d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482044"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel 関数

**Omp_in_parallel**関数は、並列で実行される並列領域の動的範囲内で呼び出された場合に 0 以外の値を返します。 それ以外の場合、0 を返します。 形式は次のとおりです。

```
#include <omp.h>
int omp_in_parallel(void);
```

この関数は、シリアル化される入れ子になったリージョンを含む、並列で実行される領域内から呼び出された場合は 0 以外の値を返します。