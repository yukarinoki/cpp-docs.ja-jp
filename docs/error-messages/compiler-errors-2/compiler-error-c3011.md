---
title: コンパイラ エラー C3011
ms.date: 11/04/2016
f1_keywords:
- C3011
helpviewer_keywords:
- C3011
ms.assetid: 24c3a917-ebff-4deb-9155-23adf6468531
ms.openlocfilehash: 453af6be844b1a3aa4f0e9c80f6b5733952c1557
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62350310"
---
# <a name="compiler-error-c3011"></a>コンパイラ エラー C3011

インライン アセンブリを、並行領域内で使用することはできません

`omp` 並列領域は、インライン アセンブリの命令を含めることはできません。

次の例では C3011 が生成されます。

```
// C3011.cpp
// compile with: /openmp
// processor: /x86
int main() {
   int   n = 0;

   #pragma omp parallel
   {
      _asm mov eax, n   // Delete this line to resolve this error.
   }   // C3011
}
```