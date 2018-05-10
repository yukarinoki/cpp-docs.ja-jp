---
title: 2.5.1 parallel for コンストラクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a233e7ed-2462-4f7a-9a5d-556ab9f363d8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef2732c4f8713466d282346ea240bd3c41886ce0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="251-parallel-for-construct"></a>2.5.1 parallel for コンストラクト
**の並列**ディレクティブは、ショートカットを**並列**が 1 つのみが含まれる領域**の**ディレクティブです。 構文、**の並列**ディレクティブは、次のようにします。  
  
```  
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop  
```  
  
 このディレクティブのすべての句を使用して、**並列**ディレクティブと**の**ディレクティブを除く、`nowait`と同じ意味と制限の句。 セマンティクスは明示的に指定することと同じ、**並列**ディレクティブの直後に続く、**の**ディレクティブです。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **並列**ディレクティブを参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。  
  
-   **デ**ィレクティブを参照してください[セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) [11] ページ。  
  
-   データ属性の句を参照してください[2.7.2 データ共有属性句](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md)[25] ページ。