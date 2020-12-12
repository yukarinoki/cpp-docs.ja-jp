---
description: 詳細については、「コンパイラエラー C3020」を参照してください。
title: コンパイラ エラー C3020
ms.date: 11/04/2016
f1_keywords:
- C3020
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
ms.openlocfilehash: b5518419b4b0d2e397ce13aad07ee030d62548bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285774"
---
# <a name="compiler-error-c3020"></a>コンパイラ エラー C3020

' var ': OpenMP ' for ' ループのインデックス変数は、ループ本体では変更できません

OpenMP ループでは、 **`for`** ループの本体のインデックス (ループカウンター) を変更できない場合があり **`for`** ます。

次の例では、C3020 が生成されます。

```cpp
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

[A.6 lastprivate](../../parallel/openmp/reference/openmp-clauses.md#lastprivate)で宣言された変数を、並列化されたループ内のインデックスとして使用することはできません。

次の例では、C3020 を2番目の a.6 lastprivate に対して指定します。これは、a.6 lastprivate が最も外側の for ループ内の idx_a への書き込みをトリガーするためです。 最初の a.6 lastprivate ではエラーが発生しません。これは、a.6 lastprivate が最も外側の for ループの外側に (技術的には最後の反復処理の最後に) idx_a への書き込みをトリガーするためです。 次の例では、C3020 が生成されます。

```cpp
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

```cpp
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
