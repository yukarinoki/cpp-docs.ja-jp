---
title: コンパイラ エラー C2974
ms.date: 11/04/2016
f1_keywords:
- C2974
helpviewer_keywords:
- C2974
ms.assetid: 1b444260-f2bf-48d7-ab1e-35573d8c4a0e
ms.openlocfilehash: 2fa0fae07435f3ab63398b7b3f02f9c662e7b436
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501375"
---
# <a name="compiler-error-c2974"></a>コンパイラ エラー C2974

無効な型引数 'number' 型が必要です。

ジェネリックまたはテンプレートの引数では、ジェネリックまたはテンプレート宣言が一致しません。 型は、山かっこ内に表示されます。 適切な種類を検索するジェネリックまたはテンプレートの定義を確認します。

次の例では、C2974 が生成されます。

```
// C2974.cpp
// C2974 expected
template <class T>
struct TC {};

template <typename T>
void tf(T){}

int main() {
   // Delete the following 2 lines to resolve
   TC<1>* tc;
   tf<"abc">("abc");

   TC<int>* tc;
   tf<const char *>("abc");
}
```

C2974 は、ジェネリックを使用しているときにも発生します。

```
// C2974b.cpp
// compile with: /clr
// C2974 expected
using namespace System;
generic <class T>
ref struct GCtype {};

generic <typename T>
void gf(T){}

int main() {
   // Delete the following 2 lines to resolve
   GCtype<"a">^ gc;
   gf<"a">("abc");

   // OK
   GCtype<int>^ gc;
   gf<String ^>("abc");
}
```