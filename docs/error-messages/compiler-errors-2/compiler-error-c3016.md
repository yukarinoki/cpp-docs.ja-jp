---
description: 詳細については、「コンパイラエラー C3016」を参照してください。
title: コンパイラ エラー C3016
ms.date: 11/04/2016
f1_keywords:
- C3016
helpviewer_keywords:
- C3016
ms.assetid: 3423467e-e8bb-4f35-b4db-7925cafa74c1
ms.openlocfilehash: e45425946993caa43cfaf1a19730ef5414a6f2d5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285865"
---
# <a name="compiler-error-c3016"></a>コンパイラ エラー C3016

'var': OpenMP 'for' ステートメントのインデックス変数は、符号付きの整数型を含んでいなければなりません

OpenMP ステートメントのインデックス変数は、 **`for`** 符号付き整数型である必要があります。

次の例では C3016 が生成されます。

```cpp
// C3016.cpp
// compile with: /openmp
int main()
{
   #pragma omp parallel
   {
      unsigned int i = 0;
      // Try the following line instead:
      // int i = 0;

      #pragma omp for
      for (i = 0; i <= 10; ++i)   // C3016
      {
      }
   }
}
```
