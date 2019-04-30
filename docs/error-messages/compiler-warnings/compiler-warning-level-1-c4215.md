---
title: コンパイラの警告 (レベル 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: a45cd6cf86eb8ab1edb33ad5e0df8374972c425e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386487"
---
# <a name="compiler-warning-level-1-c4215"></a>コンパイラの警告 (レベル 1) C4215

nonstandard extension used : long float

既定の Microsoft 拡張機能 (/Ze) が扱う**long float**として**二重**します。 ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) はありません。 使用**二重**互換性を維持します。

次の例では、C4215 が生成されます。

```
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```