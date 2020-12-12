---
description: 詳細については、「コンパイラエラー C3047」を参照してください。
title: コンパイラ エラー C3047
ms.date: 11/04/2016
f1_keywords:
- C3047
helpviewer_keywords:
- C3047
ms.assetid: 91c14566-5958-433d-8549-0e8bc3196f76
ms.openlocfilehash: 471f85f6a73e911ea9c308a3de9d2afbe800f750
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269784"
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
