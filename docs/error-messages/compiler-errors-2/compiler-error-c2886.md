---
title: コンパイラ エラー C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: 3e445b52c2a0abbfca198c4cb0f4108dd5ba5ffb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233432"
---
# <a name="compiler-error-c2886"></a>コンパイラ エラー C2886

' class:: identifier ': シンボルをメンバー using 宣言の中で使用することはできません

宣言では、 **`using`** 名前空間名などのシンボルを使用します。 **`using`** 宣言は、基底クラスのメンバーを宣言するためのものです。

次の例では、C2886 が生成されます。

```cpp
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
