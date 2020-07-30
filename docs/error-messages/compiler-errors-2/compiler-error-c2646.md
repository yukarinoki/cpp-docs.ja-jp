---
title: コンパイラエラー C2646
ms.date: 11/04/2016
f1_keywords:
- C2646
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
ms.openlocfilehash: a05c98564c4e45dc380690c1b8c9bace5fc14cf4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216155"
---
# <a name="compiler-error-c2646"></a>コンパイラエラー C2646

グローバルまたは名前空間スコープの匿名構造体または匿名共用体は静的に宣言する必要があります

匿名の構造体または共用体にはグローバルまたは名前空間スコープがありますが、宣言されていません **`static`** 。

次の例では、C2646 を生成し、その修正方法を示しています。

```cpp
// C2646.cpp
// compile with: /c
union { int i; };   // C2646 not static

// OK
static union { int j; };
union U { int i; };
```
