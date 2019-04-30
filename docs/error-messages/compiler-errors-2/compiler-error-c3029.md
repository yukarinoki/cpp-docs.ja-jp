---
title: コンパイラ エラー C3029
ms.date: 11/04/2016
f1_keywords:
- C3029
helpviewer_keywords:
- C3029
ms.assetid: 655eb04d-504a-468d-8c0c-bda1e5f297b7
ms.openlocfilehash: a003a0b8fcba3609c355ae467a11b4024a0529d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385811"
---
# <a name="compiler-error-c3029"></a>コンパイラ エラー C3029

'symbol' : OpenMP ディレクティブのデータ共有句で一度だけ使用することができます

シンボルは、ディレクティブの 1 つ以上の句で複数回使用されました。 シンボルは、ディレクティブで一度だけ使用することができます。

次の例では C3029 が生成されます。

```
// C3029.cpp
// compile with: /openmp /link vcomps.lib
#include "omp.h"

int g_i;

int main() {
   int i, x;

   #pragma omp parallel reduction(+ : x, x)   // C3029
      ;

   #pragma omp parallel reduction(+ : x)   // OK
      ;

   #pragma omp parallel private(x) reduction(+ : x)   // C3029
      ;

   #pragma omp parallel reduction(+ : x)   // OK
      ;
}
```