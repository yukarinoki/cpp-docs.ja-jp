---
title: コンパイラ エラー C2452
ms.date: 11/04/2016
f1_keywords:
- C2452
helpviewer_keywords:
- C2452
ms.assetid: a4ec7642-6660-4c7a-9866-853d1cc67daf
ms.openlocfilehash: 9b9f2c41da1eb36aceece7f14ad5c33b38404bb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523702"
---
# <a name="compiler-error-c2452"></a>コンパイラ エラー C2452

'type': safe_cast に対する無効なソースの種類

ソース型は[safe_cast](../../windows/safe-cast-cpp-component-extensions.md)が無効です。  たとえば、すべての型を`safe_cast`操作は CLR 型である必要があります。

次の例では、C2452 が生成されます。

```
// C2452.cpp
// compile with: /clr

struct A {};
struct B : public A {};

ref struct C {};
ref struct D : public C{};

int main() {
   A a;
   safe_cast<B*>(&a);   // C2452

   // OK
   C ^ c = gcnew C;
   safe_cast<D^>(c);
}
```