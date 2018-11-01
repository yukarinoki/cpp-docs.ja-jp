---
title: コンパイラ エラー C3670
ms.date: 11/04/2016
f1_keywords:
- C3670
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
ms.openlocfilehash: d3acfd9d4d09c53fac0b2c5a2462c56dfd54e6d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598550"
---
# <a name="compiler-error-c3670"></a>コンパイラ エラー C3670

'override': アクセスできない基底クラス メソッド 'method' をオーバーライドすることはできません

オーバーライドでは、アクセス レベルでは、派生型で使用可能な関数でのみ実行できます。 詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)します。

次の例では、C3670 が生成されます。

```
// C3670.cpp
// compile with: /clr /c
public ref class C {
// Uncomment the following line to resolve.
// public:
   virtual void g() { }
};

public ref class D : public C {
public:
   virtual void f() new sealed = C::g {};   // C3670
};
```