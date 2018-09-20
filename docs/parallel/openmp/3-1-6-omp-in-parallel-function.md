---
title: 3.1.6 omp_in_parallel 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ba6c35d42f8497869894bd5ec95b83f0c8793f1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404619"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel 関数

**Omp_in_parallel**関数は、並列で実行される並列領域の動的範囲内で呼び出された場合に 0 以外の値を返します。 それ以外の場合、0 を返します。 形式は次のとおりです。

```
#include <omp.h>
int omp_in_parallel(void);
```

この関数は、シリアル化される入れ子になったリージョンを含む、並列で実行される領域内から呼び出された場合は 0 以外の値を返します。