---
description: 詳細については、「コンパイラエラー C2783」を参照してください。
title: コンパイラエラー C2783
ms.date: 11/04/2016
f1_keywords:
- C2783
helpviewer_keywords:
- C2783
ms.assetid: 1ce94a11-bb8b-4be3-a222-f1f105da74b3
ms.openlocfilehash: 671a1974f94ca9e31b83861c3e1b503762ca58d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297968"
---
# <a name="compiler-error-c2783"></a>コンパイラエラー C2783

' 宣言 ': ' identifier ' のテンプレート引数を推測できませんでした

コンパイラは、テンプレート引数を特定できません。 既定の引数を使用してテンプレート引数を推定することはできません。

次の例では、C2783 が生成されます。

```cpp
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

C2783 は、ジェネリックを使用する場合にも発生する可能性があります。

```cpp
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
