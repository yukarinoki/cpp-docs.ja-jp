---
description: 詳細については、「コンパイラエラー C3037」を参照してください。
title: コンパイラ エラー C3037
ms.date: 11/04/2016
f1_keywords:
- C3037
helpviewer_keywords:
- C3037
ms.assetid: 9ba8a890-d3c7-4cce-93c5-d358e2bfad28
ms.openlocfilehash: f8ccf87ca09aaf90fb07b197279e994eeb27f249
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270057"
---
# <a name="compiler-error-c3037"></a>コンパイラ エラー C3037

'var': 'reduction' 句の変数は、それを囲むコンテキスト内で共有されなければなりません

[reduction](../../parallel/openmp/reference/openmp-clauses.md#reduction) 句で指定される変数は、コンテキスト内の各スレッドに対してプライベートにすることはできません。

次の例では C3037 が生成されます。

```cpp
// C3037.cpp
// compile with: /openmp /c
int g_i;

int main() {
   int i;

   #pragma omp parallel private(g_i)
   // try the following line instead
   // #pragma omp parallel
   {
      #pragma omp for reduction(+:g_i)   // C3037
      for (i = 0 ; i < 10 ; ++i) {
         g_i += i;
      }
   }
}
```
