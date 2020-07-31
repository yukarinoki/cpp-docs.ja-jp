---
title: コンパイラの警告 (レベル 1) C4227
ms.date: 11/04/2016
f1_keywords:
- C4227
helpviewer_keywords:
- C4227
ms.assetid: 78f98374-c00b-4000-aefa-1b1c67b4666b
ms.openlocfilehash: f5cc9e67c06443a73692ce663a2106dacff6035c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221017"
---
# <a name="compiler-warning-level-1-c4227"></a>コンパイラの警告 (レベル 1) C4227

旧形式: 参照の修飾子は無視されます

などの修飾子 **`const`** を **`volatile`** C++ 参照と共に使用することは、旧式の手法です。

## <a name="example"></a>例

```cpp
// C4227.cpp
// compile with: /W1 /c
int j = 0;
int &const i = j;   // C4227
```
