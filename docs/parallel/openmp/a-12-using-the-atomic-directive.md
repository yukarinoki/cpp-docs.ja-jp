---
title: Atomic ディレクティブを使用して A.12 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d3ba3c87-413d-4efa-8a45-8a7f28ab0164
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 719d7a9843a0759b5a5bd558e07a2004f9ef1543
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="a12---using-the-atomic-directive"></a>A.12 atomic ディレクティブの使用
次の例は、競合状態を回避できます (の要素の同時更新*x*複数のスレッドで) を使用して、`atomic`ディレクティブ ([セクション 2.6.4](../../parallel/openmp/2-6-4-atomic-construct.md) 19 ページ上)。  
  
```  
#pragma omp parallel for shared(x, y, index, n)  
    for (i=0; i<n; i++)   
    {  
        #pragma omp atomic  
            x[index[i]] += work1(i);  
        y[i] += work2(i);  
    }  
```  
  
 使用する利点、`atomic`この例ではディレクティブは、並列で実行する x の 2 つの要素を更新できます。 場合、`critical`ディレクティブ ([セクション 2.6.2](../../parallel/openmp/2-6-2-critical-construct.md) 18 ページ) の要素をすべて更新して代わりに、使用された*x*逐次的に (ただし、いずれかではなく、順序を保証) 実行されます。  
  
 なお、`atomic`ディレクティブは、C または C++ ステートメントの直後にのみ適用されます。  その結果、要素の*y*この例ではアトミックに更新されません。