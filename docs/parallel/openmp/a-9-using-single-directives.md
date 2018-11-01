---
title: A.9 single ディレクティブの使用
ms.date: 11/04/2016
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
ms.openlocfilehash: 51a2a3438ae5abc9d24c160a986c8ea04b77c4bf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501310"
---
# <a name="a9---using-single-directives"></a>A.9 single ディレクティブの使用

次の例で、`single`ディレクティブ ([セクション 2.4.3](../../parallel/openmp/2-4-3-single-construct.md) [15] ページ)。 例では、1 つのスレッドで (が発生した最初のスレッドは、通常、`single`ディレクティブ) 進行状況メッセージを出力します。 ユーザーでは、スレッドは実行には、どのような想定する必要があります加えないで、`single`セクション。 他のすべてのスレッドは、スキップ、`single`セクションし、バリアの最後で停止、`single`を構築します。 他のスレッドがスレッドの実行を待たずに進むことができるかどうか、 `single`  セクションで、`nowait`に句を指定できます、`single`ディレクティブ。

```
#pragma omp parallel
{
    #pragma omp single
        printf_s("Beginning work1.\n");
    work1();
    #pragma omp single
        printf_s("Finishing work1.\n");
    #pragma omp single nowait
        printf_s("Finished work1 and beginning work2.\n");
    work2();
}
```