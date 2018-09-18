---
title: コンパイラの警告 (レベル 1) C4114 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4114
dev_langs:
- C++
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a8d67148c2b9fb22c90013905eb246bf8d3bdf75
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067573"
---
# <a name="compiler-warning-level-1-c4114"></a>コンパイラの警告 (レベル 1) C4114

同じ型の修飾子が 2 度以上使われています。

型の宣言または定義は、型修飾子を使用して (**const**、**揮発性**、**署名**、または**符号なし**) 2 回以上。 これにより、Microsoft 拡張機能 (/Ze) での警告とエラー ANSI 互換 (/Za)。

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
