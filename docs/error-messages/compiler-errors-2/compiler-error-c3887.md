---
title: コンパイラ エラー C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: e41ea1dbe1f2bd47f9b557d502ec95bcecb1e2a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428264"
---
# <a name="compiler-error-c3887"></a>コンパイラ エラー C3887

'var': リテラル データ メンバーの初期化子は定数式である必要があります

A[リテラル](../../windows/literal-cpp-component-extensions.md)データ メンバーは定数式でのみ初期化できます。

次の例では、C3887 が生成されます。

```
// C3887.cpp
// compile with: /clr
ref struct Y1 {
   static int i = 9;
   literal
   int staticConst = i;   // C3887
};
```

考えられる解決方法:

```
// C3887b.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   int staticConst = 9;
};
```