---
title: A.6 lastprivate 句の使用
ms.date: 11/04/2016
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
ms.openlocfilehash: 7d5ba1413827590b7fb3afa0847b9aa1da3c41e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579805"
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6 lastprivate 句の使用

適切な実行場合によっては、ループの最後の反復変数に割り当てられている値に依存します。 このようなプログラムへの引数としてこのようなすべての変数を一覧する必要があります、`lastprivate`句 ([セクション 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) 27 ページの) 変数の値が、ループが順番に実行されるときと同じになるようです。

```
#pragma omp parallel
{
   #pragma omp for lastprivate(i)
      for (i=0; i<n-1; i++)
         a[i] = b[i] + b[i+1];
}
a[i]=b[i];
```

前の例の値で`i`並列領域の最後に等しい`n-1`シーケンシャル ケースのようにします。