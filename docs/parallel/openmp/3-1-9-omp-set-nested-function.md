---
title: 3.1.9 omp_set_nested 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68e5898b8b57814a152ca2ce9ced84a9df8190cc
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414540"
---
# <a name="319-ompsetnested-function"></a>3.1.9 omp_set_nested 関数

**Omp_set_nested**関数を有効または入れ子になった並列処理を無効にします。 形式は次のとおりです。

```
#include <omp.h>
void omp_set_nested(int nested);
```

場合*入れ子になった*入れ子になった 0 に評価される、これは、既定では、並列処理が無効と入れ子になった並列領域はシリアル化され、現在のスレッドによって実行します。 場合*入れ子になった*評価 0 以外の値には、入れ子になった並列処理が有効であり、入れ子になっている並列領域は入れ子になったチームを形成する追加のスレッドをデプロイできます。

この関数は、プログラムの部分から呼び出されたときに上記で説明した効果を**omp_in_parallel**関数は 0 を返します。 プログラムの部分から呼び出されたかどうか、 **omp_in_parallel**関数は 0 以外の値を返します、この関数の動作は未定義です。

この呼び出しに優先、 **OMP_NESTED**環境変数。

入れ子になった並列処理が有効にすると入れ子になった並列領域の実行に使用されるスレッドの数は実装定義です。 その結果、OpenMP に準拠した実装では、入れ子になった並列処理が有効な場合でも、入れ子になった並列領域をシリアル化許可されます。

## <a name="cross-references"></a>クロス リファレンス

- **OMP_NESTED**環境変数を参照してください[セクション 4.4](../../parallel/openmp/4-4-omp-nested.md) [49] ページ。

- **omp_in_parallel**関数を参照してください[セクション 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) 38 ページ。