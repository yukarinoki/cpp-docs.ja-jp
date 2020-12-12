---
description: 詳細については、「コンパイラエラー C3071」を参照してください。
title: コンパイラ エラー C3071
ms.date: 11/04/2016
f1_keywords:
- C3071
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
ms.openlocfilehash: f99175021b87cb9c27982121567bbb0dd97b0163
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320411"
---
# <a name="compiler-error-c3071"></a>コンパイラ エラー C3071

演算子 'operator' は、ref クラスまたは値型のインスタンスにのみ適用できます

CLR 演算子は、ネイティブ型で使用できません。 この演算子は、ref クラスや ref 構造体 (値型) で使用できますが、System::Int32 のようなネイティブ型の int やエイリアスなどのネイティブ型では使用できません。 これらの型は、ネイティブ変数を参照する方法で C++ コードからボックス化することはできません。したがって、この演算子は使用できません。

詳細については、「 [参照演算子の追跡](../../extensions/tracking-reference-operator-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では C3071 が生成されます。

```cpp
// C3071.cpp
// compile with: /clr
class N {};
ref struct R {};

int main() {
   N n;
   %n;   // C3071

   R r;
   R ^ r2 = %r;   // OK
}
```
