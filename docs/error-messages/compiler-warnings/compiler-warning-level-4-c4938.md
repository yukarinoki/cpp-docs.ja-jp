---
description: '詳細情報: コンパイラの警告 (レベル 4) C4938'
title: コンパイラの警告 (レベル 4) C4938
ms.date: 11/04/2016
f1_keywords:
- C4938
helpviewer_keywords:
- C4938
ms.assetid: 6acac81a-9d23-465e-b700-ed4b6e8edcd0
ms.openlocfilehash: 3b327581b0eb790e74d6fddc2bca1e027f40d89e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234593"
---
# <a name="compiler-warning-level-4-c4938"></a>コンパイラの警告 (レベル 4) C4938

'var' : 浮動小数点の減少変数は、/fp:strict または #pragma fenv_access で矛盾する結果を生じさせる可能性があります

合計は異なる順序で計算されるため、OpenMP の浮動小数点の減少で、 [/fp:strict](../../build/reference/fp-specify-floating-point-behavior.md) または [fenv_access](../../preprocessor/fenv-access.md) を使用しないでください。 したがって、結果は、/openmp を使用しない場合の結果と異なる可能性があります。

次の例では C4938 が生成されます。

```cpp
// C4938.cpp
// compile with: /openmp /W4 /fp:strict /c
// #pragma fenv_access(on)
extern double *a;

double test(int first, int last) {
   double sum = 0.0;
   #pragma omp parallel for reduction(+: sum)   // C4938
   for (int i = first ; i <= last ; ++i)
      sum += a[i];
   return sum;
}
```

明示的な並列化を使用しない場合、合計は次のように計算されます。

```
sum = a[first] + a[first + 1] + ... + a[last];
```

明示的な並列化 (および 2 つのスレッド) を使用する場合、合計は次のように計算されます。

```
sum1 = a[first] + ... a[first + last / 2];
sum2 = a[(first + last / 2) + 1] + ... a[last];
sum = sum1 + sum2;
```
