---
title: コンパイラ エラー C2682 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2682
dev_langs:
- C++
helpviewer_keywords:
- C2682
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72dc19170729d7203b57e305ef2c8a0d2b2d6de1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049203"
---
# <a name="compiler-error-c2682"></a>コンパイラ エラー C2682

'type1' から 'type2' に変換する casting_operator を使用することはできません。

キャスト演算子と互換性のない型を変換しようとしました。 たとえば、使用することはできません、 [dynamic_cast](../../cpp/dynamic-cast-operator.md)参照へのポインターに変換する演算子。 `dynamic_cast`演算子はキャスト修飾子を使用できることはできません。 型のすべての修飾子が一致する必要があります。

使用することができます、`const_cast`などの属性を削除するオペレーター `const`、 `volatile`、または`__unaligned`します。

次の例では、C2682 が生成されます。

```
// C2682.cpp
class A { virtual void f(); };
class B: public A {};

void g(A* pa) {
    B& rb = dynamic_cast<B&>(pa); // C2682
}
```

次の例では、C2682 が生成されます。

```
// C2682b.cpp
// compile with: /clr
ref struct R{};
ref struct RR : public R{};
ref struct H {
   RR^ r ;
   short s;
   int i;
};

int main() {
   H^ h = gcnew H();
   interior_ptr<int>lr = &(h->i);
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK
}
```