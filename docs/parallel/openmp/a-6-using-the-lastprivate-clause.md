---
title: A.6 lastprivate 句の使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf3bf0cc-aa46-4e44-9433-e2969e3be2c1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03d18d3aaf5c5d1cbe03282710ae4f4e2bb613f3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390580"
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