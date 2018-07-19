---
title: 重要なディレクティブを使用して A.5 |Microsoft ドキュメント
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
ms.openlocfilehash: c1a41e9664faaca24b6708c737a044828eb460bd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686257"
---
# <a name="a5---using-the-critical-directive"></a>A.5 critical ディレクティブの使用
次の例では、いくつか含まれています`critical`ディレクティブ ([セクション 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) 18 ページ)。 この例では、タスクがキューから削除して作業対象のキューのモデルを示します。 同じタスクをキューから削除する複数のスレッドを防ぐには、デキュー操作に必要な`critical`セクションです。 によって保護されているため、この例では 2 つのキューは独立して、 `critical` 、異なる名前のディレクティブ*xaxis*と*yaxis*です。  
  
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