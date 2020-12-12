---
description: '詳細情報: コンパイラの警告 (レベル 1) C4114'
title: コンパイラの警告 (レベル 1) C4114
ms.date: 11/04/2016
f1_keywords:
- C4114
helpviewer_keywords:
- C4114
ms.assetid: 3983e1c6-e8bb-46dc-8894-e1827db48797
ms.openlocfilehash: 7d1d7696fabdf8e5114ba733f7bf6de53353bcb4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267444"
---
# <a name="compiler-warning-level-1-c4114"></a>コンパイラの警告 (レベル 1) C4114

同じ型の修飾子が 2 度以上使われています。

型宣言または定義で、型修飾子 ( **`const`** 、 **`volatile`** 、 **`signed`** 、または **`unsigned`** ) を複数回使用しています。 これにより、Microsoft 拡張機能 (/Ze) で警告が発生し、ANSI 互換 (/Za) でエラーが発生します。

次の例では、C4114 が生成されます。

```cpp
// C4114.cpp
// compile with: /W1 /c
volatile volatile int i;   // C4114
```

次の例では、C4114 が生成されます。

```cpp
// C4114_b.cpp
// compile with: /W1 /c
static const int const * ii;   // C4114
static const int * const iii;   // OK
```
