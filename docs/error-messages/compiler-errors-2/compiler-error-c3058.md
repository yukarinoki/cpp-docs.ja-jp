---
description: 詳細については、「コンパイラエラー C3058」を参照してください。
title: コンパイラ エラー C3058
ms.date: 11/04/2016
f1_keywords:
- C3058
helpviewer_keywords:
- C3058
ms.assetid: 669d08c8-0b58-4351-88aa-c6e6e1af481c
ms.openlocfilehash: 9a7c4c3fa4fd8186055985ff66caa3ffd0c4f081
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269459"
---
# <a name="compiler-error-c3058"></a>コンパイラ エラー C3058

'symbol' : シンボルは、'copyin' 句の中で使用される前に 'threadprivate' として宣言されていません

シンボルは、 [copyin](../../parallel/openmp/reference/openmp-directives.md#threadprivate) 句で使用する前に、最初に [threadprivate](../../parallel/openmp/reference/openmp-clauses.md#copyin) として宣言されている必要があります。

次の例では C3058 が生成されます。

```cpp
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

考えられる解決策:

```cpp
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
