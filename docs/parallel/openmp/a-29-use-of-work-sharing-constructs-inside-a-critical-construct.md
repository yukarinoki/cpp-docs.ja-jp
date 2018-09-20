---
title: A.29 使用の作業の共有内でコンストラクト critical コンストラクト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d5c8a83f-2f51-4f23-8ddf-d267e347507f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8574687d8fa037e0adca908e3aa761a2619d26a8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46424145"
---
# <a name="a29---use-of-work-sharing-constructs-inside-a-critical-construct"></a>A.29 critical コンストラクト内での work-sharing コンストラクトの使用

次の例での work-sharing コンス トラクター内でを使用して、`critical`を構築します。 この例は、作業の共有を構築ために準拠していると、`critical`コンス トラクターは、同じ並列領域をバインドしないでください。

```
void f()
{
  int i = 1;
  #pragma omp parallel sections
  {
    #pragma omp section
    {
      #pragma omp critical (name)
      {
        #pragma omp parallel
        {
          #pragma omp single
          {
            i++;
          }
        }
      }
    }
  }
}
```