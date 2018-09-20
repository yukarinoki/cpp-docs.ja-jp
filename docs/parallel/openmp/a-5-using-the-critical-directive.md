---
title: A.5 critical ディレクティブの使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 14423018-25b9-4f98-92f2-34c9b0ac0ce0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99f9ab513ae1df5a7e1e62cfefcefe404637c063
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46444568"
---
# <a name="a5---using-the-critical-directive"></a>A.5 critical ディレクティブの使用

次の例では、いくつか含まれています`critical`ディレクティブ ([セクション 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) 18 ページ)。 この例では、タスクがキューから削除され作業キューのモデルを使用します。 複数のスレッドが同じタスクをキューからの保護、デキュー操作がである必要があります、`critical`セクション。 によって保護されているため、この例では、2 つのキューは独立して、 `critical` 、異なる名前のディレクティブ*xaxis*と*yaxis*します。

```
#pragma omp parallel shared(x, y) private(x_next, y_next)
{
    #pragma omp critical ( xaxis )
        x_next = dequeue(x);
    work(x_next);
    #pragma omp critical ( yaxis )
        y_next = dequeue(y);
    work(y_next);
}
```