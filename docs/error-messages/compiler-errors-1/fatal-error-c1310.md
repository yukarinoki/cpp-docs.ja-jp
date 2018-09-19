---
title: 致命的なエラー C1310 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1310
dev_langs:
- C++
helpviewer_keywords:
- C1310
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2890177619500e7041d5edb0993789e244d17e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46095587"
---
# <a name="fatal-error-c1310"></a>致命的なエラー C1310

ガイド付き最適化のプロファイルは OpenMP と共に使用できません

[/GL](../../build/reference/ltcg-link-time-code-generation.md) を使用してコンパイルしたモジュールを [/LTCG:PGI](../../build/reference/gl-whole-program-optimization.md)でリンクさせることはできません。

次の例では C1310 が生成されます。

```
// C1310.cpp
// compile with: /openmp /GL /link /LTCG:PGI
// C1310 expected
int main()
{
   int i = 0, j = 10;

   #pragma omp parallel
   {
      #pragma omp for
      for (i = 0; i < 0; i++)
         --j;
   }
}
```