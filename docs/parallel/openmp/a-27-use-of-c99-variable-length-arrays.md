---
title: A.27 C99 可変長配列の使用
ms.date: 11/04/2016
ms.assetid: 8e542701-39f9-4f28-ab3a-840e8e669723
ms.openlocfilehash: 7b2ee74dcd5adedd02e7a9b311c5d3f67203d892
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655300"
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