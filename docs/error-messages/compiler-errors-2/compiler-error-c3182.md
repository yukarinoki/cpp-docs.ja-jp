---
title: コンパイラ エラー C3182
ms.date: 11/04/2016
f1_keywords:
- C3182
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
ms.openlocfilehash: 6866c7bbcee0a4097e490b344c79a6eec7f94570
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626747"
---
# <a name="compiler-error-c3182"></a>コンパイラ エラー C3182

'class': メンバーを使用して宣言または access 宣言は、マネージ型または WinRTtype 内で有効ですが

A[を使用して](../../cpp/using-declaration.md)宣言がマネージ クラスのすべてのフォーム内で無効です。

次の例では C3182 が生成され、その修正方法が示されています。

```
// C3182a.cpp
// compile with: /clr /c
ref struct B {
   void mf(int) {
   }
};

ref struct D : B {
   using B::mf;   // C3182, delete to resolve
   void mf(char) {
   }
};
```
