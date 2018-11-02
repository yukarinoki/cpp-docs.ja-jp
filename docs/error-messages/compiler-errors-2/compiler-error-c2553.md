---
title: コンパイラ エラー C2553
ms.date: 11/04/2016
f1_keywords:
- C2553
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
ms.openlocfilehash: 11cb2b83d958f0c59d05034a716a022f00b326ec
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50658680"
---
# <a name="compiler-error-c2553"></a>コンパイラ エラー C2553

'base_function': 'override_function' とは異なる型を返す仮想関数のオーバーライド

派生クラスの関数は、基底クラスの仮想関数をオーバーライドしようとしていますが、派生クラスの関数は、基本クラスの関数の戻り値型がありませんでした。  オーバーライド関数のシグネチャは、オーバーライドされる関数のシグネチャに一致する必要があります。

次の例では、C2553 が生成されます。

```
// C2553.cpp
// compile with: /clr /c
ref struct C {
   virtual void f();
};

ref struct D : C {
   virtual int f() override ;   // C2553

   // try the following line instead
   // virtual void f() override;
};
```