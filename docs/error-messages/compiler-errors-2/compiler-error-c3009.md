---
title: コンパイラ エラー C3009
ms.date: 11/04/2016
f1_keywords:
- C3009
helpviewer_keywords:
- C3009
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
ms.openlocfilehash: a1f4a20396e97c6b868a5678958970813b638499
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597198"
---
# <a name="compiler-error-c3009"></a>コンパイラ エラー C3009

'label': OpenMP 構造化ブロックへのジャンプは許可されていません

コードは、OpenMP ブロックの内部または外部にジャンプできません。

次の例では C3009 が生成されます。

```
// C3009.c
// compile with: /openmp
int main() {
   #pragma omp parallel
   {
   lbl2:;
   }
   goto lbl2;   // C3009
}
```