---
description: 詳細については、「コンパイラエラー C2387」を参照してください。
title: コンパイラ エラー C2387
ms.date: 11/04/2016
f1_keywords:
- C2387
helpviewer_keywords:
- C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
ms.openlocfilehash: 70c876c999ec7d40b93ac94ffe111d105981ceeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124008"
---
# <a name="compiler-error-c2387"></a>コンパイラ エラー C2387

' type ': あいまいな基底クラスです。

コンパイラは、関数が複数の基底クラスに存在するため、関数呼び出しを明確に解決できませんでした。

このエラーを解決するには、いずれかの基底クラスを継承から削除するか、関数呼び出しを明示的に修飾します。

次の例では、C2387 が生成されます。

```cpp
// C2387.cpp
namespace N1 {
   struct B {
      virtual void f() {
      }
   };
}

namespace N2 {
   struct B {
      virtual void f() {
      }
   };
}

struct D : N1::B, N2::B {
   virtual void f() {
      B::f();   // C2387
      // try the following line instead
      // N1::B::f();
   }
};

int main() {
   D aD;
   aD.f();
}
```
