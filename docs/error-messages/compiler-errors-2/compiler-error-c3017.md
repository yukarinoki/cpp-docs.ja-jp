---
description: 詳細については、「コンパイラエラー C3017」を参照してください。
title: コンパイラ エラー C3017
ms.date: 11/04/2016
f1_keywords:
- C3017
helpviewer_keywords:
- C3017
ms.assetid: 12ab2c2a-d0d2-4900-9cbf-39be0af590dd
ms.openlocfilehash: bbfffbb9d9f9b0c34dbf0dab57c28d7fd6892fd9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285839"
---
# <a name="compiler-error-c3017"></a>コンパイラ エラー C3017

OpenMP 'for' ステートメントの終了テストには、正しくない形式が含まれています

**`for`** OpenMP ステートメント内のループは、完全かつ明示的に指定されている必要があります。

次の例では C3017 が生成されます。

```cpp
// C3017.cpp
// compile with: /openmp
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i; ++i)   // C3017
      // Try the following line instead:
      // for (i = 0; i < 10; ++i)
         ;
   }
}
```
