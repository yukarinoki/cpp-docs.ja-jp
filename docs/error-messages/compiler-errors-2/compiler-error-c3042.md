---
title: コンパイラ エラー C3042 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3042
dev_langs:
- C++
helpviewer_keywords:
- C3042
ms.assetid: bf73f61e-5bd2-40a8-9b06-6244e6a15a41
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 36fde6251244582a0626c80aa673ed6dd0e559d2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045227"
---
# <a name="compiler-error-c3042"></a>コンパイラ エラー C3042

'copyprivate' 句および 'nowait' 句は、OpenMP 'directive' ディレクティブで同時に使用することはできません

[copyprivate](../../parallel/openmp/reference/copyprivate.md) 句と [nowait](../../parallel/openmp/reference/nowait.md) 句は、指定されたディレクティブでは同時に使用できません。 このエラーを解決するには、 `copyprivate` 句か `nowait` 句の一方または両方を削除します。

次の例では C3042 が生成されます。

```
// C3042.cpp
// compile with: /openmp /c
#include <stdio.h>
#include "omp.h"

double d;

int main() {
    #pragma omp parallel private(d)
   {
      #pragma omp single copyprivate(d) nowait   // C3042
      {
      }
   }
}
```