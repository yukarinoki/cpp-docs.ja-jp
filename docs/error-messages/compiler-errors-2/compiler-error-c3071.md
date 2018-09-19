---
title: コンパイラ エラー C3071 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3071
dev_langs:
- C++
helpviewer_keywords:
- C3071
ms.assetid: 69879e66-a60e-4058-9bbd-d5c5e2d8ee37
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5f004de3ed133ea77d543014ae1adcdc4e1eddef
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077803"
---
# <a name="compiler-error-c3071"></a>コンパイラ エラー C3071

演算子 'operator' は、ref クラスまたは値型のインスタンスにのみ適用できます

CLR 演算子は、ネイティブ型で使用できません。 この演算子は、ref クラスや ref 構造体 (値型) で使用できますが、System::Int32 のようなネイティブ型の int やエイリアスなどのネイティブ型では使用できません。 これらの型は、ネイティブ変数を参照する方法で C++ コードからボックス化することはできません。したがって、この演算子は使用できません。

詳細については、次を参照してください。[参照演算子の追跡](../../windows/tracking-reference-operator-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では C3071 が生成されます。

```
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