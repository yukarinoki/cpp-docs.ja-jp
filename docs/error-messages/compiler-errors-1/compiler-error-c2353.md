---
title: コンパイラ エラー C2353
ms.date: 11/04/2016
f1_keywords:
- C2353
helpviewer_keywords:
- C2353
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
ms.openlocfilehash: 3cfcb544349adc0b7b4e13472f70aac382f958fd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516997"
---
# <a name="compiler-error-c2353"></a>コンパイラ エラー C2353

例外の指定は許可されていません

例外の仕様は、マネージ クラスのメンバー関数では許可されません。

次の例では、C2353 が生成されます。

```
// C2353.cpp
// compile with: /clr /c
ref class X {
   void f() throw(int);   // C2353
   void f();   // OK
};
```