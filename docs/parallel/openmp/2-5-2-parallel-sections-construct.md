---
title: 2.5.2 parallel sections のコンストラクト |Microsoft Docs
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
ms.openlocfilehash: 073d0561fe4bfbb96ed88681a077da6fc985c963
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402331"
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