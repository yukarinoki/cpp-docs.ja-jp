---
title: コンパイラの警告 (レベル 1) C4216
ms.date: 11/04/2016
f1_keywords:
- C4216
helpviewer_keywords:
- C4216
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
ms.openlocfilehash: 43c72855dbb40e93cb219e4461dbbf81d086ea79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650919"
---
# <a name="compiler-warning-level-1-c4216"></a>コンパイラの警告 (レベル 1) C4216

使用される標準の拡張機能: long float

既定の Microsoft 拡張機能 (/Ze) が扱う**long float**として**二重**します。 ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) はありません。 使用**二重**互換性を維持します。 次の例では、C4216 が生成されます。

```
// C4216.cpp
// compile with: /W1
float long a;   // C4216

// use the line below to resolve the warning
// double a;

int main() {
}
```