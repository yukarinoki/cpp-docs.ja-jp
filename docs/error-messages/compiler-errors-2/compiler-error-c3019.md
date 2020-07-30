---
title: コンパイラ エラー C3019
ms.date: 11/04/2016
f1_keywords:
- C3019
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
ms.openlocfilehash: 5275ee6dd6680da3bf3aae0b657997f264762163
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232041"
---
# <a name="compiler-error-c3019"></a>コンパイラ エラー C3019

OpenMP ' for ' ステートメントのインクリメントには、正しくない形式が含まれています

OpenMP ループのインクリメント部分では、 **`for`** 演算子の左辺と右辺の両方でインデックス変数を使用する必要があります。

次の例では、C3019 が生成されます。

```cpp
// C3019.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 1, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i = j + n)   // C3019
      // Try the following line instead:
      // for (i = 0; i < 10; i++)
         j *= 2;
   }
}
```
