---
description: 詳細については、「コンパイラエラー C3040」を参照してください。
title: コンパイラ エラー C3040
ms.date: 11/04/2016
f1_keywords:
- C3040
helpviewer_keywords:
- C3040
ms.assetid: 29e857ac-74f0-4ec6-becf-9026e38c160e
ms.openlocfilehash: e43f7e6e63d7ec2462247a9846febd4c0b4eab4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269937"
---
# <a name="compiler-error-c3040"></a>コンパイラ エラー C3040

'var': 'reduction' 句の変数の型は、減少演算子 'operator' と互換性がありません

[reduction](../../parallel/openmp/reference/openmp-clauses.md#reduction) 句内の変数は、減少演算子では使用できません。

次の例では C3040 が生成されます。

```cpp
// C3040.cpp
// compile with: /openmp /c
#include "omp.h"
double d;

int main() {
   #pragma omp parallel reduction(&:d)   // C3040
      ;

   #pragma omp parallel reduction(-:d)  // OK
      ;
}
```
