---
description: 詳細については、「コンパイラエラー C3182」を参照してください。
title: コンパイラエラー C3182
ms.date: 11/04/2016
f1_keywords:
- C3182
helpviewer_keywords:
- C3182
ms.assetid: f3681266-308e-4990-a979-8eef8920e186
ms.openlocfilehash: d4cf5d86a553a597636c09f72ff3a068e2a6b9b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242029"
---
# <a name="compiler-error-c3182"></a>コンパイラエラー C3182

' class ': マネージまたは WinRTtype の中で、メンバーの using 宣言またはアクセス宣言は無効です

[Using](../../cpp/using-declaration.md)宣言は、すべての形式のマネージクラス内では無効です。

次の例では C3182 が生成され、その修正方法が示されています。

```cpp
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
