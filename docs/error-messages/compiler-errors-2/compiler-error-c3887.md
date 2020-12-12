---
description: 詳細については、「コンパイラエラー C3887」を参照してください。
title: コンパイラ エラー C3887
ms.date: 11/04/2016
f1_keywords:
- C3887
helpviewer_keywords:
- C3887
ms.assetid: a7e82426-ef99-437b-9562-2822004e18fe
ms.openlocfilehash: 8c80a1ff54f56e111934ebc370fee28f011bd37b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97274347"
---
# <a name="compiler-error-c3887"></a>コンパイラ エラー C3887

' var ': リテラルデータメンバーの初期化子は定数式でなければなりません

[リテラル](../../extensions/literal-cpp-component-extensions.md)データメンバーは、定数式を使用してのみ初期化できます。

次の例では、C3887 が生成されます。

```cpp
// C3887.cpp
// compile with: /clr
ref struct Y1 {
   static int i = 9;
   literal
   int staticConst = i;   // C3887
};
```

考えられる解決策:

```cpp
// C3887b.cpp
// compile with: /clr /c
ref struct Y1 {
   literal
   int staticConst = 9;
};
```
