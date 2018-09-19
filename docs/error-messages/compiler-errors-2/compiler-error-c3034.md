---
title: コンパイラ エラー C3034 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3034
dev_langs:
- C++
helpviewer_keywords:
- C3034
ms.assetid: 49db8bac-2720-4622-94e3-7988f1603fa3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e3d96e975450241a5baae60758beadfe40dbe5e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46091466"
---
# <a name="compiler-error-c3034"></a>コンパイラ エラー C3034

OpenMP 'directive1' ディレクティブを、'directive2' ディレクティブの中に直接入れ子にすることはできません

一部のディレクティブは入れ子にできません。 このエラーを修正するには、1 つのディレクティブのブロックに両方のディレクティブのステートメントをマージするか、または連続するディレクティブを作成します。

次の例では C3034 が生成されます。

```
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