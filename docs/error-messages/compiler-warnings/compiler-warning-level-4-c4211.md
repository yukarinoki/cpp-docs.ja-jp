---
title: コンパイラの警告 (レベル 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: df19f90e17d6737a2639eb1245da197881e35c96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218105"
---
# <a name="compiler-warning-level-4-c4211"></a>コンパイラの警告 (レベル 4) C4211

非標準の拡張が使用されています: extern を static に再定義します

既定の Microsoft 拡張機能 (/Ze) では、識別子をとして再定義でき **`extern`** **`static`** ます。

## <a name="example"></a>例

```c
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

このような再定義は ANSI 互換 ([/za](../../build/reference/za-ze-disable-language-extensions.md)) では無効です。
