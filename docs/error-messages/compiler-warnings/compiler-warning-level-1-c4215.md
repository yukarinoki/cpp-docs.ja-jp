---
title: コンパイラの警告 (レベル 1) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: b62f382759c7e4c9dc888cf75d4df07a063df571
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199863"
---
# <a name="compiler-warning-level-1-c4215"></a>コンパイラの警告 (レベル 1) C4215

非標準の拡張機能が使用されています: long float

既定の Microsoft 拡張機能 (/Ze) では、 **long float**は**double**として扱われます。 ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) ではありません。 互換性を維持するには、 **double**を使用します。

次の例では、C4215 が生成されます。

```cpp
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```
