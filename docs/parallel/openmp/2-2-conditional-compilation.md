---
title: 2.2 条件付きコンパイル
ms.date: 11/04/2016
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
ms.openlocfilehash: 9dc107ee9e5328df205d4b6f826f71c23abfb3ba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658550"
---
# <a name="22-conditional-compilation"></a>2.2 条件付きコンパイル

_**OPENMP**マクロ名は 10 進定数として OpenMP に準拠した実装で定義されている*yyyymm*、承認済みの仕様の月と年になります。 このマクロの件名をすることはできません、 **#define**または **#undef**プリプロセス ディレクティブ。

```
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

ベンダーは、openmp の拡張機能を定義する場合は追加の定義済みマクロを指定します。