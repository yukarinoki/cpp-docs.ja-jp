---
title: コンパイラ エラー C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: 68672ae76024d3d09d738d997c485a3205c7dd2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588062"
---
# <a name="compiler-error-c2133"></a>コンパイラ エラー C2133

'identifier': サイズが不明です

可変長配列は、クラス、構造体、共用体、または列挙体のメンバーとして宣言されます。 /Za (ANSI C) オプションでは、メンバーを可変長配列は許可されません。

次の例では、C2133 が生成されます。

```
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

考えられる解決方法:

```
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```