---
title: コンパイラ エラー C3015
ms.date: 11/04/2016
f1_keywords:
- C3015
helpviewer_keywords:
- C3015
ms.assetid: d5e8e50b-7542-4b2d-8665-1b22072a5bc6
ms.openlocfilehash: db87b035d76d4e3d2cf3f05c30ebddf0b6d22d5e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232106"
---
# <a name="compiler-error-c3015"></a>コンパイラ エラー C3015

OpenMP 'for' ステートメントの初期化には、正しくない形式が含まれています

**`for`** OpenMP ステートメント内のループは、完全かつ明示的に指定されている必要があります。

次の例では C3015 が生成されます。

```cpp
// C3015.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (; i < 0; i += j)   // C3015
      // Try the following line instead:
      // for (i = 0; i < 0; i++)
         --j;
   }
}
```
