---
title: 3.2.1 omp_init_lock 関数と omp_init_nest_lock 関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 098a2721-b16a-484f-bc83-4b8e281e382c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4303eb3ccfcb1c449022a4be32f94b9f91e6e80c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387004"
---
# <a name="321-ompinitlock-and-ompinitnestlock-functions"></a>3.2.1 omp_init_lock 関数と omp_init_nest_lock 関数

これらの関数は、ロックの初期化の唯一の手段を提供します。 各関数の初期化パラメーターに関連付けられているロック*ロック*後続の呼び出しで使用します。 形式は次のとおりです。

```
#include <omp.h>
void omp_init_lock(omp_lock_t *lock);
void omp_init_nest_lock(omp_nest_lock_t *lock);
```

初期状態がロックされている (つまり、スレッド ロックを所有していません)。 入れ子にできるロックでは、入れ子の最初の数は 0 です。 これらのルーチンには、既に初期化されているロック変数のいずれかを呼び出さない非準拠になります。