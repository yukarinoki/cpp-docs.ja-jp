---
title: 致命的なエラー C1310
ms.date: 11/04/2016
f1_keywords:
- C1310
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
ms.openlocfilehash: 1b0fca9a5e453fd354a4efc6960a54386795ccf6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559059"
---
# <a name="fatal-error-c1310"></a>致命的なエラー C1310

ガイド付き最適化のプロファイルは OpenMP と共に使用できません

[/GL](../../build/reference/ltcg-link-time-code-generation.md) を使用してコンパイルしたモジュールを [/LTCG:PGI](../../build/reference/gl-whole-program-optimization.md)でリンクさせることはできません。

次の例では C1310 が生成されます。

```
// C1310.cpp
// compile with: /openmp /GL /link /LTCG:PGI
// C1310 expected
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 0; i++)
         --j;
   }
}
```