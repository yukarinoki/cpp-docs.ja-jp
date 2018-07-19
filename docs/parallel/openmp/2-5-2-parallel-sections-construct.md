---
title: 2.5.2 parallel sections のコンストラクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6f7a84e322cb273733c6a724ee2563928df8362
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689481"
---
# <a name="252-parallel-sections-construct"></a>2.5.2 parallel sections のコンストラクト
**Parallel sections の**ディレクティブを指定するショートカット フォームを提供する、**並列**が 1 つのみが含まれる領域**セクション**ディレクティブです。 セマンティクスは明示的に指定することと同じ、**並列**ディレクティブの直後に続く、**セクション**ディレクティブです。 構文、 **parallel sections の**ディレクティブは、次のようにします。  
  
```  
#pragma omp parallel sections  [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block  ]  
   ...  
}  
```  
  
 *句*で受け入れられる句のいずれかになります、**並列**と**のセクションでは**、ディレクティブを除く、 **nowait**句。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **並列**ディレクティブを参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページのです。  
  
-   **セクションでは**ディレクティブを参照してください[2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) [14] ページ。