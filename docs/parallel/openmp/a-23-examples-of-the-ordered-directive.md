---
title: 順序付けられたディレクティブの例については A.23 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f8fa761b-7fc5-4447-95f9-8571e9ca31bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37cc4ea9db8cbd1a7bf095e2bde0ae482053a584
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692757"
---
# <a name="a23---examples-of-the-ordered-directive"></a>A.23 ordered ディレクティブの例
順序付けられた複数のセクションを取得することは、`for`で指定された、`ordered`句。 最初の例は、API は、次を指定するために準拠していません。  
  
 "でループのイテレーション、`for`コンストラクト実行してはいけません同じ`ordered`と、それ以上のディレクティブは 1 つ以上を実行できません必要があります`ordered`ディレクティブです"。 (を参照してください[セクション 2.6.6](../../parallel/openmp/2-6-6-ordered-construct.md) 22 ページ上)  
  
 この規則違反の例では、すべてのイテレーションは、2 つの順序付けられたセクションを実行します。  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
    #pragma omp ordered  
    { ... }  
    ...  
}  
```  
  
 準拠している例を次に、`for`順序付けられた複数のセクション。  
  
```  
#pragma omp for ordered  
for (i=0; i<n; i++)   
{  
    ...  
    if (i <= 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
    (i > 10)   
    {  
        ...  
        #pragma omp ordered  
        { ... }  
    }  
    ...  
}  
```