---
title: コンパイラ エラー C3182 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3182
dev_langs:
- C++
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 722f95b41f9f5ec467af25ccf927631590f90e45
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110220"
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
