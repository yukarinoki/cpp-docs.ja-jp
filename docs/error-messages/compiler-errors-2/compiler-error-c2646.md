---
title: コンパイラ エラー C2646
ms.date: 11/04/2016
f1_keywords:
- C2646
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
ms.openlocfilehash: c02d7216df42681ae2ec733ae932d22861c1f0ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572007"
---
# <a name="compiler-error-c2646"></a>コンパイラ エラー C2646

グローバルまたは名前空間スコープの匿名構造体または匿名共用体は静的に宣言する必要があります

匿名構造体または匿名共用体にはグローバル スコープまたは名前空間のスコープがありますが、`static` 宣言されていません。

次の例では、C2646 を生成し、その修正方法を示しています。

```
// C2646.cpp
// compile with: /c
union { int i; };   // C2646 not static

// OK
static union { int j; };
union U { int i; };
```