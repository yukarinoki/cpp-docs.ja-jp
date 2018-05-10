---
title: 2.4.2 sections のコンストラクト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 20b24c5b7d2458294da6280acb2ba7e8be5961fb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="242-sections-construct"></a>2.4.2 sections のコンストラクト
**セクション**ディレクティブを識別、noniterative work-sharing コンス トラクターの構造体をチーム内のスレッドに分割するにはセットを指定します。 各セクションでは、チーム内のスレッドで 1 回実行されます。 構文、**セクション**ディレクティブは、次のようにします。  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block ]  
...  
}  
```  
  
 句では、次のいずれかです。  
  
 **private(** *variable-list* **)**  
  
 **firstprivate(** *variable-list* **)**  
  
 **lastprivate(** *variable-list* **)**  
  
 **reduction(** *operator* **:**  *variable-list* **)**  
  
 **nowait**  
  
 各セクションの後、**セクション**ディレクティブ、ですが、**セクション**ディレクティブは、最初のセクションでは省略可能です。 **セクション**ディレクティブはの構文上の範囲内でなければなりません。、**セクション**ディレクティブです。 暗黙的なバリアの末尾には、**セクション**しない限り、構築、 **nowait**が指定されています。  
  
 制限は、**セクション**ディレクティブは、次のとおり。  
  
-   A**セクション**の構文の範囲外ディレクティブが含まれなければ、**セクション**ディレクティブです。  
  
-   1 つだけ**nowait**句に表示できる、**セクション**ディレクティブです。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **プライベート**、 **firstprivate**、 **lastprivate**、および**削減**句を参照してください[セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) [25] ページ。