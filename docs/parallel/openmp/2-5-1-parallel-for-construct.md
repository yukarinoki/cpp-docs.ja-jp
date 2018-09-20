---
title: 2.5.1 parallel for コンストラクト |Microsoft Docs
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
ms.openlocfilehash: cfff3b0c17dd098b5d802af61a7ca1f81cb02845
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373962"
---
# <a name="251-parallel-for-construct"></a>2.5.1 parallel for コンストラクト

**の並列**ディレクティブは、ショートカット、**並列**が 1 つのみを含む領域**の**ディレクティブ。 構文、**の並列**ディレクティブを次に示します。

```
#pragma omp parallel for [clause[[,] clause] ...] new-linefor-loop
```

このディレクティブのすべての句を使用して、**並列**ディレクティブと**の**ディレクティブを除く、`nowait`と同じ意味と制限の句。 セマンティクスは明示的に指定するのと同じであり、**並列**ディレクティブの直後に続く、**の**ディレクティブ。

## <a name="cross-references"></a>クロス リファレンス

- **並列**ディレクティブを参照してください[セクション 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 ページの。

- **ディ**レクティブを参照してください[セクション 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) [11] ページ。

- データ属性句を参照してください[2.7.2 データ共有属性句](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md)25 ページにします。