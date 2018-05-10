---
title: 2.4.3 コンス トラクターの 1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db3f9ca834fb3f35c95732698fd02e16f31b4225
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="243-single-construct"></a>2.4.3 single コンストラクト
**単一**ディレクティブが関連付けられている構造化ブロックが、チーム (必ずしもマスター スレッド) 内の 1 つだけのスレッドによって実行されることを指定する構成を識別します。 構文、**単一**ディレクティブは、次のようにします。  
  
```  
#pragma omp single [clause[[,] clause] ...] new-linestructured-block  
```  
  
 句では、次のいずれかです。  
  
 **private(** *variable-list* **)**  
  
 **firstprivate(** *variable-list* **)**  
  
 **copyprivate (** *変数一覧* **)**  
  
 **nowait**  
  
 後に、暗黙的な障害物が、**単一**れない限り、作成、 **nowait**句を指定します。  
  
 制限は、**単一**ディレクティブは、次のとおり。  
  
-   1 つだけ**nowait**句に表示できる、**単一**ディレクティブです。  
  
-   **Copyprivate**に句を使用しないでください、 **nowait**句。  
  
## <a name="cross-references"></a>クロス リファレンス  
  
-   **プライベート**、 **firstprivate**、および**copyprivate**句を参照してください[セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) [25] ページ。