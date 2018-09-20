---
title: 3.1.8 omp_get_dynamic 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c30f49eaf91353d6a7cd9bd26e0e10e95cb6acd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426784"
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 omp_get_dynamic 関数

**Omp_get_dynamic**関数は、スレッドの動的な調整が有効であり、それ以外の場合は 0 を返す場合に 0 以外の値を返します。 形式は次のとおりです。

```
#include <omp.h>
int omp_get_dynamic(void);
```

実装がスレッドの数を動的に調整を実装していない場合、この関数は常に 0 を返します。

## <a name="cross-references"></a>クロス リファレンス

- 動的なスレッドの調整については、次を参照してください。[セクション 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) 39 ページ。