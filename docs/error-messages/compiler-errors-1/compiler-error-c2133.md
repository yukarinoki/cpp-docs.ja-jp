---
description: 詳細については、「コンパイラエラー C2133」を参照してください。
title: コンパイラ エラー C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: d98cb3bd8df5543ecf0426a146157300f67dd91b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323130"
---
# <a name="compiler-error-c2133"></a>コンパイラ エラー C2133

' identifier ': サイズが不明です

可変長配列は、クラス、構造体、共用体、または列挙体のメンバーとして宣言されます。 /Za (ANSI C) オプションでは、可変長メンバー配列は許可されません。

次の例では、C2133 が生成されます。

```cpp
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

考えられる解決策:

```cpp
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```
