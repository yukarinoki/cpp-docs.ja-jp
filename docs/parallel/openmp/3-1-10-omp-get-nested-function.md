---
title: 3.1.10 omp_get_nested 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d019dd757080bbc87ff7aaab1a8745b2a3156b39
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392282"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested 関数

`omp_get_nested`関数 0 を返します 0 以外の値を使用している場合、入れ子になった並列処理が有効になっている場合は無効になります。 入れ子になった並列処理の詳細については、40 ページの 3.1.9 セクションを参照してください。 形式は次のとおりです。

```
#include <omp.h>
int omp_get_nested(void);
```

実装が入れ子になった並列処理を実装していない場合、この関数は常に 0 を返します。