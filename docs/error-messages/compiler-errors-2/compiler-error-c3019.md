---
title: コンパイラ エラー C3019
ms.date: 11/04/2016
f1_keywords:
- C3019
helpviewer_keywords:
- C3019
ms.assetid: 31a6d9b6-d29f-4499-9ad8-48dd751e87c7
ms.openlocfilehash: bba90917614cbc8facb182659c288f9823d8ab45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432554"
---
# <a name="compiler-error-c3019"></a>コンパイラ エラー C3019

openmp 'for' ステートメントの増分値が正しくない形式

OpenMP のインクリメント部分`for`ループ インデックス変数、演算子の右側にある左右の両方を使用する必要があります。

次の例では、C3019 が生成されます。

```
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