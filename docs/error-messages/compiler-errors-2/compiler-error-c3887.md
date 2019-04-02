---
title: コンパイラ エラー C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: 85434cb8daba0db82843c09e2d1bb09d98960272
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777442"
---
# <a name="compiler-error-c3887"></a>コンパイラ エラー C3887

'var': リテラル データ メンバーの初期化子は定数式である必要があります

A[リテラル](../../extensions/literal-cpp-component-extensions.md)データ メンバーは定数式でのみ初期化できます。

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