---
description: 詳細については、「コンパイラエラー C3006」を参照してください。
title: コンパイラ エラー C3006
ms.date: 11/04/2016
f1_keywords:
- C3006
helpviewer_keywords:
- C3006
ms.assetid: 449082ec-fd45-4c47-8ab3-ba6a719e4dc4
ms.openlocfilehash: e2c6372b86f7677f3beeaed5335798f10e01c82e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274555"
---
# <a name="compiler-error-c3006"></a>コンパイラ エラー C3006

'clause': OpenMP 'directive' ディレクティブ上の句には、必要な引数がありません

OpenMP ディレクティブに必要な引数がありません。

次の例では C3006 が生成されます。

```c
// C3006.c
// compile with: /openmp
int main()
{
   #pragma omp parallel shared   // C3006
   // Try the following line instead:
   // #pragma omp parallel shared(x) {}

}
```
