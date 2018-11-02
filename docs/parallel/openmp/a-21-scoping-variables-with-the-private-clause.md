---
title: A.21 private 句付きのスコープ変数
ms.date: 11/04/2016
ms.assetid: 7cdb4a7f-af24-44ac-9d33-e43840bc8f3d
ms.openlocfilehash: 4217bcc3911ded88b9385695c8c0ac851fceae9e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616129"
---
# <a name="a21---scoping-variables-with-the-private-clause"></a>A.21 private 句付きのスコープ変数

値`i`と`j`次の例では、並列領域からの終了時に未定義です。

```
int i, j;
i = 1;
j = 2;
#pragma omp parallel private(i) firstprivate(j)
{
  i = 3;
  j = j + 2;
}
printf_s("%d %d\n", i, j);
```

詳細については、`private`句を参照してください[セクション 2.7.2.1](../../parallel/openmp/2-7-2-1-private.md) 25 ページにします。