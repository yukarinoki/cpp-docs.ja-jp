---
title: A.27 C99 可変長配列の使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8e542701-39f9-4f28-ab3a-840e8e669723
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51fda970f78592c8a4e10d17d370e9c78f0ea493
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405893"
---
# <a name="a27---use-of-c99-variable-length-arrays"></a>A.27 C99 可変長配列の使用

次の例では、C99 可変長配列 (Vla) を使用する方法を示しますで、`firstprivate`ディレクティブ ([2.7.2.2 セクション](../../parallel/openmp/2-7-2-2-firstprivate.md)[26] ページ)。

> [!NOTE]
>  可変長配列は、Visual C では現在サポートされていません。

```
void f(int m, int C[m][m])
{
    double v1[m];
    ...
    #pragma omp parallel firstprivate(C, v1)
    ...
}
```