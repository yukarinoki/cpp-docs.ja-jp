---
title: A.29 critical コンストラクト内での work-sharing コンストラクトの使用
ms.date: 11/04/2016
ms.assetid: d5c8a83f-2f51-4f23-8ddf-d267e347507f
ms.openlocfilehash: fac5576f859f63298d658b51c4307bb238e301c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643587"
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