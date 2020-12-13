---
description: 詳細については、「コンパイラエラー C2886」を参照してください。
title: コンパイラ エラー C2886
ms.date: 11/04/2016
f1_keywords:
- C2886
helpviewer_keywords:
- C2886
ms.assetid: c01588a1-484c-4dc9-a3f1-f900c6e44543
ms.openlocfilehash: 0a2591a18fc7113b77f90e689860906d35fa9460
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337475"
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
