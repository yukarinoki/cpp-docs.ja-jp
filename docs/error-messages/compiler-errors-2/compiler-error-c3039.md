---
title: コンパイラ エラー C3039
ms.date: 11/04/2016
f1_keywords:
- C3039
helpviewer_keywords:
- C3039
ms.assetid: 02776f16-f57a-4ffd-b7f7-9c696b633e08
ms.openlocfilehash: 69be1b25254119108e517cee2f1e14368e0163f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511619"
---
# <a name="compiler-error-c3039"></a>コンパイラ エラー C3039

'var' : OpenMP 'for' ステートメントのインデックス変数を減少変数にすることはできません

インデックス変数は暗黙的にプライベートであるため、囲む [parallel](../../parallel/openmp/reference/reduction.md) ディレクティブ内の [reduction](../../parallel/openmp/reference/parallel.md) 句で、変数を使用することはできません。

## <a name="example"></a>例

次の例では C3039 が生成されます。

```
// C3039.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel reduction(+: i)
   {
      #pragma omp for
      for (i = 0; i < 10; ++i)   // C3039
         g_i += i;
   }
}
```