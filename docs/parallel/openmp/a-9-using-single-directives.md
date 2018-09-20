---
title: A.9 single ディレクティブの使用 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0c0f9495-5794-4db9-883b-a12e3a9f1328
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a3a201450d54355aa96f0ea712ad9fa0f70f63f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46448091"
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