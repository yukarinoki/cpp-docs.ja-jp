---
title: コンパイラ エラー C3052
ms.date: 11/04/2016
f1_keywords:
- C3052
helpviewer_keywords:
- C3052
ms.assetid: 87480c42-1ceb-4775-8d20-88c54a7bb6a6
ms.openlocfilehash: 40857432e07baffea69d8201cc3e0241698c93da
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91506204"
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
