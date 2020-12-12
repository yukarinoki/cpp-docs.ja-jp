---
description: 詳細については、「コンパイラエラー C3009」を参照してください。
title: コンパイラ エラー C3009
ms.date: 11/04/2016
f1_keywords:
- C3009
helpviewer_keywords:
- C3009
ms.assetid: aded5985-f5fd-4c3e-a157-16be55ec1313
ms.openlocfilehash: fd261901293fd002465f4767f2b4389e1c388614
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305326"
---
# <a name="compiler-error-c3009"></a>コンパイラ エラー C3009

'label': OpenMP 構造化ブロックへのジャンプは許可されていません

コードは、OpenMP ブロックの内部または外部にジャンプできません。

次の例では C3009 が生成されます。

```c
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
