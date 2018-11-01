---
title: A.8 並行セクションの指定
ms.date: 11/04/2016
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
ms.openlocfilehash: 81eaed920e77b23052ac58c2d0e18fee83c00565
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461439"
---
# <a name="a8---specifying-parallel-sections"></a>A.8 並行セクションの指定

次の例では、(の[2.4.2](../../parallel/openmp/2-4-2-sections-construct.md) [14] ページ) 関数*xaxis*、 *yaxis*、および*zaxis*同時に実行することができます。 最初の`section`ディレクティブは省略可能です。  なおすべて`section`ディレクティブはの構文の範囲で表示する必要があります、`parallel sections`を構築します。

```
#pragma omp parallel sections
{
    #pragma omp section
        xaxis();
    #pragma omp section
        yaxis();
    #pragma omp section
        zaxis();
}
```