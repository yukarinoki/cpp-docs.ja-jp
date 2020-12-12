---
description: 詳細については、「コンパイラエラー C3055」を参照してください。
title: コンパイラ エラー C3055
ms.date: 11/04/2016
f1_keywords:
- C3055
helpviewer_keywords:
- C3055
ms.assetid: 60446ee0-18dd-48fc-9059-f0a14229dce8
ms.openlocfilehash: 6c75d476abf7535499c74705e4a0ec77d80dc772
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269576"
---
# <a name="compiler-error-c3055"></a>コンパイラ エラー C3055

'symbol' : 'threadprivate' ディレクティブの中で使用される前に、シンボルを参照することはできません

シンボルが参照されてから [threadprivate](../../parallel/openmp/reference/openmp-directives.md#threadprivate) 句で使用されました。これは許可されていません。

次の例では C3055 が生成されます。

```cpp
// C3055.cpp
// compile with: /openmp
int x, y;
int z = x;
#pragma omp threadprivate(x, y)   // C3055

void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

考えられる解決策:

```cpp
// C3055b.cpp
// compile with: /openmp /LD
int x, y, z;
#pragma omp threadprivate(x, y)

void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```
