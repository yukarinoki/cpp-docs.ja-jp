---
description: 詳細については、「コンパイラエラー C2353」を参照してください。
title: コンパイラ エラー C2353
ms.date: 11/04/2016
f1_keywords:
- C2353
helpviewer_keywords:
- C2353
ms.assetid: d57f8f77-d9b1-4bba-a940-87ec269ad183
ms.openlocfilehash: d2fc96a74256f37b6c7cb9bc9515d46ad70fd83d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291884"
---
# <a name="compiler-error-c2353"></a>コンパイラ エラー C2353

例外指定は許可されていません

マネージクラスのメンバー関数では、例外の指定は許可されません。

次の例では、C2353 が生成されます。

```cpp
// C2353.cpp
// compile with: /clr /c
ref class X {
   void f() throw(int);   // C2353
   void f();   // OK
};
```
