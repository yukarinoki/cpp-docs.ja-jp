---
description: 詳細については、「コンパイラエラー C2902」を参照してください。
title: コンパイラ エラー C2902
ms.date: 11/04/2016
f1_keywords:
- C2902
helpviewer_keywords:
- C2902
ms.assetid: 89d78d0e-78e5-4c2c-a0f9-a60110e9395e
ms.openlocfilehash: 45e58615e6bd2465489da7059a350ef476b705a9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270759"
---
# <a name="compiler-error-c2902"></a>コンパイラ エラー C2902

'token' : 'template' の予期しないトークンです。識別子が必要です

キーワードに続くトークン **`template`** が識別子ではありませんでした。

次の例では C2902 が生成されます。

```cpp
// C2902.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template + 1;   // C2902
}

void f() {
   N::template X<int> x1;   // OK
}
```

C2902 は、ジェネリックを使用しているときも発生することがあります。

```cpp
// C2902b.cpp
// compile with: /clr /c
namespace N {
   generic<class T> ref class GC {};
}

void f() {
   N::generic + 1;   // C2902
   N::generic GC<int>^ x;
}
```
