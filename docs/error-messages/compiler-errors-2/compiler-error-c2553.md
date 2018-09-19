---
title: コンパイラ エラー C2553 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2553
dev_langs:
- C++
helpviewer_keywords:
- C2553
ms.assetid: 64bc1e9a-627f-4ce9-b7bc-dc911bdb9180
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 38fb61b7281dd0371c546fd7b7bc960232cf2e00
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043990"
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