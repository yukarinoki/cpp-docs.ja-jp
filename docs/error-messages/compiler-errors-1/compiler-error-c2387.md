---
title: コンパイラ エラー C2387 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2387
dev_langs:
- C++
helpviewer_keywords:
- C2387
ms.assetid: 6847b8e1-ffac-458d-ab88-0c92f72f2527
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a73f2964c7f87ba795ba680947664a0f37b9c303
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46089620"
---
# <a name="compiler-error-c2387"></a>コンパイラ エラー C2387

'type': あいまいな基底クラス

コンパイラ明確を解決できませんでした関数呼び出し、関数が 1 つ以上の基底クラスに存在するためです。

このエラーを解決するには、継承から基底クラスのいずれかを削除するか、関数呼び出しを明示的に修飾します。

次の例では、C2387 が生成されます。

```
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