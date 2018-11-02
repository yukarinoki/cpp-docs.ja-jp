---
title: コンパイラ エラー C3058
ms.date: 11/04/2016
f1_keywords:
- C3058
helpviewer_keywords:
- C3058
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
ms.openlocfilehash: 5655fe8ebeb8f1b61d7acbba5313c2e3ab2a2b4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547239"
---
# <a name="compiler-error-c3058"></a>コンパイラ エラー C3058

'symbol' : シンボルは、'copyin' 句の中で使用される前に 'threadprivate' として宣言されていません

シンボルは、 [copyin](../../parallel/openmp/reference/threadprivate.md) 句で使用する前に、最初に [threadprivate](../../parallel/openmp/reference/copyin.md) として宣言されている必要があります。

次の例では C3058 が生成されます。

```
// C3058.cpp
// compile with: /openmp
int x, y, z;
#pragma omp threadprivate(x, z)

void test() {
   #pragma omp parallel copyin(x, y)   // C3058
   {
   }
}
```

考えられる解決方法:

```
// C3058b.cpp
// compile with: /openmp /LD
int x, y, z;
#pragma omp threadprivate(x, y)

void test() {
   #pragma omp parallel copyin(x, y)
   {
   }
}
```