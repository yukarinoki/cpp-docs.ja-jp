---
title: コンパイラ エラー C3883
ms.date: 11/04/2016
f1_keywords:
- C3883
helpviewer_keywords:
- C3883
ms.assetid: cdd1c1f4-f268-4469-9c62-d52303114b0c
ms.openlocfilehash: 51ecf5fbc793c02a23e2aa02fb08e37ebe4b0ad0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559771"
---
# <a name="compiler-error-c3883"></a>コンパイラ エラー C3883

'var': initonly 静的データ メンバーを初期化する必要があります

マークされた変数[initonly](../../dotnet/initonly-cpp-cli.md)正しく初期化されませんでした。

次の例では、C3883 が生成されます。

```
// C3883.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   static int staticConst1;   // C3883
};
```

次の例では、考えられる解決策を示しています。

```
// C3883b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst2 = 0;
};
```

次の例では、静的コンス トラクターで初期化する方法を示します。

```
// C3883c.cpp
// compile with: /clr /LD
ref struct Y1 {
   initonly
   static int staticConst1;

   static Y1() {
      staticConst1 = 0;
   }
};
```