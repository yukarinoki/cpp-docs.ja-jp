---
description: 詳細については、「コンパイラエラー C3036」を参照してください。
title: コンパイラ エラー C3036
ms.date: 11/04/2016
f1_keywords:
- C3036
helpviewer_keywords:
- C3036
ms.assetid: 10c6993e-bc42-4a07-85c7-cdc34ac30906
ms.openlocfilehash: 812d57ca405cafc25037a5fd933d5e3ea260e24d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270109"
---
# <a name="compiler-error-c3036"></a>コンパイラ エラー C3036

'operator': OpenMP 'reduction' 句の無効な演算子トークンです

[reduction](../../parallel/openmp/reference/openmp-clauses.md#reduction) 句を正しく指定しませんでした。

次の例では警告 C3036 が生成されます。

```cpp
// C3036.cpp
// compile with: /openmp
static float a[1000], b[1000], c[1000];
void test1(int first, int last) {
   static float dp = 0.0f;
   #pragma omp for nowait reduction(.:dp)   // C3036
   // try the following line instead
   // #pragma omp for nowait reduction(+: dp)
   for (int i = first ; i <= last ; ++i)
      dp += a[i] * b[i];
}
```
