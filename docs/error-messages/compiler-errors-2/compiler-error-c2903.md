---
title: コンパイラ エラー C2903
ms.date: 11/04/2016
f1_keywords:
- C2903
helpviewer_keywords:
- C2903
ms.assetid: bf6b223f-4921-48c7-82b9-ff318b42c801
ms.openlocfilehash: 7002e45770c994d5cd10e1cd632561be57246086
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442823"
---
# <a name="compiler-error-c2903"></a>コンパイラ エラー C2903

'identifier' : シンボルがクラス テンプレートでも関数テンプレートでもありません

コードで、テンプレートではないものを明示的にインスタンス化しようとしています。

次の例では C2903 が生成されます。

```
// C2903.cpp
// compile with: /c
namespace N {
   template<class T> class X {};
   class Y {};
}
void g() {
   N::template Y y;   // C2903
   N::X<N::Y> y;   // OK
}
```

C2903 は、ジェネリックを使用しているときにも発生します。

```
// C2903b.cpp
// compile with: /clr /c
namespace N {
   class Y {};
   generic<class T> ref class Z {};
}

void f() {
   N::generic Y y;   // C2903
   N:: generic Z<int>^ z;   // OK
}
```