---
title: コンパイラ エラー C2783
ms.date: 11/04/2016
f1_keywords:
- C2783
helpviewer_keywords:
- C2783
ms.assetid: 1ce94a11-bb8b-4be3-a222-f1f105da74b3
ms.openlocfilehash: 539eeebc39fa7fc061cc615f29d87d3e6bcfc5c8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649983"
---
# <a name="compiler-error-c2783"></a>コンパイラ エラー C2783

'declaration': 'identifier' のテンプレート引数を推測できませんでした

コンパイラは、テンプレート引数を特定できません。 既定の引数は、テンプレート引数の推測を使用できません。

次の例では、C2783 が生成されます。

```
// C2783.cpp
template<typename T1, typename T2>
T1 f(T2) {
   return 248;
}

int main() {
   f(1);   // C2783
   // try the following line instead
   int i = f<int>(1);
}
```

C2783 は、ジェネリックを使用しているときにも発生します。

```
// C2783b.cpp
// compile with: /clr
using namespace System;
generic<typename T1, typename T2>
T1 gf(T2) {
   T1 t1 = safe_cast<T1>( Activator::CreateInstance(T1::typeid));
   return t1;
}

ref class MyClass{};

int main() {
   int i;
   i = gf(9);   // C2783

   // OK
   i = gf<int>(9);
}
```