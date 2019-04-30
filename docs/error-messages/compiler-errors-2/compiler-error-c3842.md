---
title: コンパイラ エラー C3842
ms.date: 11/04/2016
f1_keywords:
- C3842
helpviewer_keywords:
- C3842
ms.assetid: 41a1a44a-c618-40a2-8d26-7da27d14095d
ms.openlocfilehash: a61a69aca53f7f8996d0261a57b749930ecc01cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385512"
---
# <a name="compiler-error-c3842"></a>コンパイラ エラー C3842

WinRT またはマネージド型のメンバー関数に対する 'function': 'const' および 'volatile' 修飾子はサポートされていません

[const](../../cpp/const-cpp.md)と[揮発性](../../cpp/volatile-cpp.md)は Windows ランタイムまたはマネージ型のメンバー関数ではサポートされていません。

次の例では C3842 が生成されます。

```
// C3842a.cpp
// compile with: /clr /c
public ref struct A {
   void f() const {}   // C3842
   void f() volatile {}   // C3842

   void f() {}
};
```