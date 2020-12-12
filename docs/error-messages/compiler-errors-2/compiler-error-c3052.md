---
description: 詳細については、「コンパイラエラー C3052」を参照してください。
title: コンパイラ エラー C3052
ms.date: 11/04/2016
f1_keywords:
- C3052
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
ms.openlocfilehash: d9d4ecf6082de02c3a4cec6486b2718a101b22d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269654"
---
# <a name="compiler-error-c3052"></a>コンパイラ エラー C3052

'var': 変数が、default(none) 句の下のデータ共有句に使用されていません

[default(none)](../../parallel/openmp/reference/openmp-clauses.md#default-openmp) が使用されている場合は、構造化ブロックで使用される変数を明示的に [shared](../../parallel/openmp/reference/openmp-clauses.md#shared-openmp) または [private](../../parallel/openmp/reference/openmp-clauses.md#private-openmp)として指定する必要があります。

次の例では C3052 が生成されます。

```cpp
// C3052.cpp
// compile with: /openmp /c
int main() {
   int n1 = 1;

   #pragma omp parallel default(none) // shared(n1) private(n1)
   {
      n1 = 0;   // C3052 use either a shared or private clause
   }
}
```
