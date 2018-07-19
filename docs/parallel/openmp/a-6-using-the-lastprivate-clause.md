---
title: Lastprivate 句を使用して A.6 |Microsoft ドキュメント
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
ms.openlocfilehash: eec6ddc46aab36671e767963e5aaf6e25c4d25cd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690544"
---
# <a name="a6---using-the-lastprivate-clause"></a>A.6 lastprivate 句の使用
正しい実行場合によっては、ループの最後の反復変数に代入する値に依存します。 このようなプログラムへの引数としてこのようなすべての変数を一覧表示する必要があります、`lastprivate`句 ([セクション 2.7.2.3](../../parallel/openmp/2-7-2-3-lastprivate.md) [27] ページ) できるように、変数の値は、ループが順番に実行されるときと同じです。  
  
```  
#pragma omp parallel  
{  
   #pragma omp for lastprivate(i)  
      for (i=0; i<n-1; i++)  
         a[i] = b[i] + b[i+1];  
}  
a[i]=b[i];  
```  
  
 前の例では、値で`i`並列領域の末尾が等しくなる`n-1`順次実行の場合のように、します。