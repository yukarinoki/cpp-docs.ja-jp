---
title: 単純なループを並列に実行される A.1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98b2fbac6ce31d2dbc56a4ef6d9fe87c14d5ee16
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686127"
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1 単純ループの並列実行
次の例を使用して、単純なループを並列化する方法を示します、`parallel for`ディレクティブ ([セクション 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) [16] ページ)。 ループの反復変数は既定では、プライベート private 句で明示的に指定する必要はありません。  
  
```  
#pragma omp parallel for  
    for (i=1; i<n; i++)  
        b[i] = (a[i] + a[i-1]) / 2.0;  
```