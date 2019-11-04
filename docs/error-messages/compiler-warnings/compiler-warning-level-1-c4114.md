---
title: コンパイラの警告 (レベル 1) C4114
ms.date: 11/04/2016
f1_keywords:
- C4114
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
ms.openlocfilehash: 41e951e7c4a8b23ddbec14c5421f66702e70c937
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300259"
---
# <a name="compiler-warning-level-1-c4114"></a>コンパイラの警告 (レベル 1) C4114

同じ型の修飾子が 2 度以上使われています。

型の宣言または定義は、型修飾子を使用して (**const**、**volatile**、**signed**、または**unsigned**) 2 回以上。 これにより、Microsoft 拡張機能 (/Ze) での警告とエラー ANSI 互換 (/Za)。

次の例では、C4114 が生成されます。

```
// C4114.cpp
// compile with: /W1 /c
volatile volatile int i;   // C4114
```

次の例では、C4114 が生成されます。

```
// C4114_b.cpp
// compile with: /W1 /c
static const int const * ii;   // C4114
static const int * const iii;   // OK
```
