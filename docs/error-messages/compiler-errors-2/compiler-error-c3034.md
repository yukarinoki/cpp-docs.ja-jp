---
description: 詳細については、「コンパイラエラー C3034」を参照してください。
title: コンパイラ エラー C3034
ms.date: 11/04/2016
f1_keywords:
- C3034
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
ms.openlocfilehash: 379fedfe3af65b2def83d737daeccac670838c2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270174"
---
# <a name="compiler-error-c3034"></a>コンパイラ エラー C3034

OpenMP 'directive1' ディレクティブを、'directive2' ディレクティブの中に直接入れ子にすることはできません

一部のディレクティブは入れ子にできません。 このエラーを修正するには、1 つのディレクティブのブロックに両方のディレクティブのステートメントをマージするか、または連続するディレクティブを作成します。

次の例では C3034 が生成されます。

```cpp
// C3034.cpp
// compile with: /openmp /link vcomps.lib
int main() {

   #pragma omp single
   {
      #pragma omp single   // C3034
      {
      ;
      }
   }

   // Two consecutive single clauses are OK.
   #pragma omp single
   {
   }

   #pragma omp single
   {
   }
}
```
