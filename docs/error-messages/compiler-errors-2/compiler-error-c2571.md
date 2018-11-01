---
title: コンパイラ エラー C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: d7d4898e5f0b55c50a4c18cef053cc150394d7e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485073"
---
# <a name="compiler-error-c2571"></a>コンパイラ エラー C2571

'function': 仮想関数は、共用体 'union' にすることはできません

仮想関数を持つ共用体が宣言されています。 クラスまたは構造体でのみ仮想関数を宣言することができます。  考えられる解決策:

1. クラスまたは構造体、共用体に変更します。

1. 非仮想関数を作成します。

次の例では、C2571 が生成されます。

```
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```