---
title: 2.2 条件付きコンパイル |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25b52ce624777efe85e27b8ce5e7941bc2f5dcba
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440382"
---
# <a name="22-conditional-compilation"></a>2.2 条件付きコンパイル

_**OPENMP**マクロ名は 10 進定数として OpenMP に準拠した実装で定義されている*yyyymm*、承認済みの仕様の月と年になります。 このマクロの件名をすることはできません、 **#define**または **#undef**プリプロセス ディレクティブ。

```
#ifdef _OPENMP
iam = omp_get_thread_num() + index;
#endif
```

ベンダーは、openmp の拡張機能を定義する場合は追加の定義済みマクロを指定します。