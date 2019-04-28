---
title: コンパイラ エラー C3055
ms.date: 11/04/2016
f1_keywords:
- C3055
helpviewer_keywords:
- C3055
ms.assetid: 60446ee0-18dd-48fc-9059-f0a14229dce8
ms.openlocfilehash: 2a770709b4958f446e8e5a64b245f2932f99460f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265582"
---
# <a name="compiler-error-c3055"></a>コンパイラ エラー C3055

'symbol' : 'threadprivate' ディレクティブの中で使用される前に、シンボルを参照することはできません

シンボルが参照されてから [threadprivate](../../parallel/openmp/reference/threadprivate.md) 句で使用されました。これは許可されていません。

次の例では C3055 が生成されます。

```
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

考えられる解決方法:

```
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