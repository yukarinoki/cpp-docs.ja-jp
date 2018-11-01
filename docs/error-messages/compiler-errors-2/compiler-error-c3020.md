---
title: コンパイラ エラー C3020
ms.date: 11/04/2016
f1_keywords:
- C3020
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
ms.openlocfilehash: 0e2d8e70dcc9b23c56a321487cd4b933a1086387
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491274"
---
# <a name="compiler-error-c3020"></a>コンパイラ エラー C3020

'var': OpenMP の 'for' ループのインデックス変数は、ループの本体では変更できません

OpenMP`for`ループ (ループ カウンター) の本文内のインデックスを変更できない、`for`ループします。

次の例では、C3020 が生成されます。

```
// C3020.cpp
// compile with: /openmp
int main() {
   int i = 0, n = 3;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 10; i += n)
         i *= 2;   // C3020
         // try the following line instead
         // n++;
   }
}
```

宣言された変数[lastprivate](../../parallel/openmp/reference/lastprivate.md)並列化されたループ内でのインデックスとして使用できません。

次の例は、その lastprivate が for ループ内で最も外側の idx_a への書き込みをトリガーするための 2 つ目の lastprivate C3020 が提供されます。 最初の lastprivate でエラーは、その lastprivate for ループ (技術的には、最後に、最後のイテレーション) 最も外側の外部 idx_a への書き込みをトリガーするためです。 次の例では、C3020 が生成されます。

```
// C3020b.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_a)   // C3020
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```

次の例では、考えられる解決策を示しています。

```
// C3020c.cpp
// compile with: /openmp /c
float a[100][100];
int idx_a, idx_b;
void test(int first, int last)
{
   #pragma omp parallel for lastprivate(idx_a)
   for (idx_a = first; idx_a <= last; ++idx_a) {
      #pragma omp parallel for lastprivate(idx_b)
      for (idx_b = first; idx_b <= last; ++idx_b) {
         a[idx_a][idx_b] += 1.0f;
      }
   }
}
```