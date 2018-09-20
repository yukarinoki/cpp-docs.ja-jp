---
title: A.8 並行セクションの指定 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: cf399304-121e-4c07-9829-47e0dbc2ef10
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d969f1a0e9d9b282104ee00a3b2d06610533ad4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440421"
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