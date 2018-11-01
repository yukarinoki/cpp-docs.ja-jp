---
title: コンパイラ エラー C3027
ms.date: 11/04/2016
f1_keywords:
- C3027
helpviewer_keywords:
- C3027
ms.assetid: 6562a5c2-2f28-4b36-91ca-2a64c0f0501a
ms.openlocfilehash: 4fa01d6fe29aa010c877c7352563d20b3a6943c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588137"
---
# <a name="compiler-error-c3027"></a>コンパイラ エラー C3027

'clause' : 演算またはポインター式が必要です

演算またはポインター式を必要とする句に、別の種類の式が渡されました。

## <a name="example"></a>例

次の例では C3027 が生成されます。

```
// C3027.cpp
// compile with: /openmp /link vcomps.lib
#include <stdio.h>
#include "omp.h"

struct MyStruct
{
    int x;
} m_MyStruct;

int main()
{
    int i;

    puts("Test with class MyStruct:\n");
    #pragma omp parallel for if(m_MyStruct)   // C3027
    for (i = 1; i <= 2; ++i)
        printf_s("Hello World - thread %d - iteration %d\n",
                 omp_get_thread_num(), i);

    puts("Test with int:\n");
    #pragma omp parallel for if(9)   // OK
    for (i = 1; i <= 2; ++i)
        printf_s("Hello World - thread %d - iteration %d\n",
                 omp_get_thread_num(), i);
}
```