---
description: 詳細については、「コンパイラエラー C3007」を参照してください。
title: コンパイラ エラー C3007
ms.date: 11/04/2016
f1_keywords:
- C3007
helpviewer_keywords:
- C3007
ms.assetid: e415ef42-bdc9-4f32-8198-5e25b289a089
ms.openlocfilehash: 5203dd3d81d2e255f13e21e66cd961413db11a18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305352"
---
# <a name="compiler-error-c3007"></a>コンパイラ エラー C3007

'arg' : OpenMP 'directive' ディレクティブ上の句には、引数を指定できません

OpenMP ディレクティブに引数が含まれていましたが、このディレクティブは引数を取りません。

次の例では C3007 が生成されます。

```c
// C3007.c
// compile with: /openmp
int main()
{
   #pragma omp parallel for ordered(2)   // C3007
}
```
