---
description: 詳細については、「コンパイラエラー C3024」を参照してください。
title: コンパイラ エラー C3024
ms.date: 11/04/2016
f1_keywords:
- C3024
helpviewer_keywords:
- C3024
ms.assetid: 1c031c28-ce37-4de3-aead-cfe76b261856
ms.openlocfilehash: 840cbb173e6dd9fe5f5ebe76076b75883849f934
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174300"
---
# <a name="compiler-error-c3024"></a>コンパイラ エラー C3024

'schedule(runtime)' : chunk_size 式は使用できません

値をスケジュール句の実行時パラメーターに渡すことはできません。

次の例では C3024 が生成されます。

```cpp
// C3024.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

int main() {
   int i;

   #pragma omp parallel for schedule(runtime, 10)   // C3024
   for (i = 0; i < 10; ++i) ;

   #pragma omp parallel for schedule(runtime)   // OK
   for (i = 0; i < 10; ++i) ;
}
```
