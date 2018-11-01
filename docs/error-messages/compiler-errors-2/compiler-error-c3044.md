---
title: コンパイラ エラー C3044
ms.date: 11/04/2016
f1_keywords:
- C3044
helpviewer_keywords:
- C3044
ms.assetid: 9f3e25b2-4676-49ab-97bf-6c88cd0fa377
ms.openlocfilehash: 0fb63d63ce9bdf0979382887164056dcdb288bd2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648163"
---
# <a name="compiler-error-c3044"></a>コンパイラ エラー C3044

'section' : OpenMP 'sections' ディレクティブの直下でのみ入れ子にすることができます

コンパイラによって、 `section` ディレクティブが正しく使用されていないことが検出されました。 詳細については、「 [sections](../../parallel/openmp/reference/sections-openmp.md)」を参照してください。

次の例では C3044 が生成されます。

```
// C3044.cpp
// compile with: /openmp /c
#include "omp.h"
int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {
         ++n2;
      }

      #pragma omp section   // C3044
      {
         ++n3;
      }
   }

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {
         #pragma omp section   // OK
         {
            ++n3;
         }
      }
   }
}
```