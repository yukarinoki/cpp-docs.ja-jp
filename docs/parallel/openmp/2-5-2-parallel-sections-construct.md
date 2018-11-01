---
title: 2.5.2 parallel sections のコンストラクト
ms.date: 11/04/2016
ms.assetid: 94220e27-14f8-465c-bd8d-eb960b4b5dee
ms.openlocfilehash: 1b74dacb9730a14364d7202918ae195cbf691955
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533667"
---
# <a name="252-parallel-sections-construct"></a>2.5.2 parallel sections のコンストラクト

**のセクションでは並列**ディレクティブを指定するためのショートカットのフォームを提供します、**並列**リージョンの 1 つだけを格納している**セクション**ディレクティブ。 セマンティクスは明示的に指定するのと同じ、**並列**ディレクティブの直後に続く、**のセクションでは**ディレクティブ。 構文、**のセクションでは並列**ディレクティブのとおりです。

```
#pragma omp parallel sections  [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block  ]
   ...
}
```

*句*で受け入れられる句のいずれか、**並列**と**セクション**ディレクティブ、以外、 **nowait**句。

## <a name="cross-references"></a>クロス リファレンス

- **並列**ディレクティブを参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの。

- **セクション**ディレクティブを参照してください[2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) [14] ページ。