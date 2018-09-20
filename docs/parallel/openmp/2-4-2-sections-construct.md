---
title: 2.4.2 sections のコンストラクト |Microsoft Docs
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
ms.openlocfilehash: 35ae940e37b40cbb9c883c4d7d6bca7b0fa65520
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410549"
---
# <a name="242-sections-construct"></a>2.4.2 sections のコンストラクト

**セクション**ディレクティブは、チーム内のスレッド間で分配する構成要素のセットを示す noniterative の work-sharing コンストラクトを識別します。 各セクションは、チーム内のスレッドで 1 回実行されます。 構文、**セクション**ディレクティブを次に示します。

```
#pragma omp sections [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block ]
...
}
```

句は、次のいずれか。

**private(** *variable-list* **)**

**firstprivate(** *variable-list* **)**

**lastprivate(** *variable-list* **)**

**reduction(** *operator* **:**  *variable-list* **)**

**nowait**

各セクションは、前に、**セクション**ディレクティブが、**セクション**ディレクティブは、最初のセクションを省略できます。 **セクション**ディレクティブはの構文範囲内でなければなりません。、**セクション**ディレクティブ。 最後に、暗黙的な壁が、**のセクションでは**しない限り、構築、 **nowait**が指定されてです。

制限は、**セクション**ディレクティブは、次のとおり。

- A**セクション**の構文の範囲外ディレクティブが表示されない必要があります、**セクション**ディレクティブ。

- 1 つだけ**nowait**句に表示できる、**セクション**ディレクティブ。

## <a name="cross-references"></a>クロス リファレンス

- **プライベート**、 **firstprivate**、 **lastprivate**、および**削減**句を参照してください[セクション 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) 25 ページにします。