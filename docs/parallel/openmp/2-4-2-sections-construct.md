---
title: 2.4.2 sections のコンストラクト
ms.date: 11/04/2016
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
ms.openlocfilehash: 2d9fca08eecd382c9d3df60159c13ac188a1ab85
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486815"
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