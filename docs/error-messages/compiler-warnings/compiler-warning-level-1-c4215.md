---
title: コンパイラの警告 (レベル 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: aeab5a90647015a8848d7c2af62f7d7fc6932900
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223279"
---
# <a name="compiler-warning-level-1-c4215"></a>コンパイラの警告 (レベル 1) C4215

非標準の拡張機能が使用されています: long float

既定の Microsoft 拡張機能 (/Ze) では、 **long float**はとして扱わ **`double`** れます。 ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) ではありません。 **`double`** 互換性を維持するには、を使用します。

次の例では、C4215 が生成されます。

```cpp
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```
