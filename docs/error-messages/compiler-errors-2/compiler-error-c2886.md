---
title: コンパイラ エラー C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: 2fa7450f03505501c2c4a45023dbb6a86937bb9c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388814"
---
# <a name="compiler-error-c2886"></a>コンパイラ エラー C2886

':identifier': シンボルをメンバー using 宣言で使用することはできません

A`using`宣言は名前空間の名前などのシンボルを使用します。 A`using`宣言が基底クラスのメンバーを宣言することです。

次の例では、C2886 が生成されます。

```
// C2886.cpp
// compile with: /c
namespace Z {
    int i;
}

class B {
protected:
    int i;
};

class D : public B {
    // Error: Z is a namespace
    using Z::i;   // C2886

    // OK: B is a base class
    using B::i;
};
```