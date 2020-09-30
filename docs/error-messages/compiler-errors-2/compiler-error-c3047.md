---
title: コンパイラ エラー C3047
ms.date: 11/04/2016
f1_keywords:
- C3047
helpviewer_keywords:
- C3047
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
ms.openlocfilehash: 41312e09996e2fe007cdc13c0369b5154e720841
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506213"
---
# <a name="compiler-error-c3047"></a>コンパイラ エラー C3047

OpenMP 'sections' 領域の構造化ブロックの前には '#pragma omp section' が必要です

[セクション](../../parallel/openmp/reference/openmp-directives.md#sections-openmp) ディレクティブによって導入されるコード ブロック内のすべてのコードは、 `section` ディレクティブによって導入されるコード ブロック内にある必要があります。

次の例では C3047 が生成されます。

```cpp
// C3047.cpp
// compile with: /openmp /c
#include "omp.h"

int main() {
   int n2 = 2, n3 = 3;

   #pragma omp parallel
   {
      ++n2;

      #pragma omp sections
      {

         #pragma omp section
         {
            ++n3;
         }

         ++n2;   // C3047 not enclosed in #pragma omp section
      }
   }
}
```
