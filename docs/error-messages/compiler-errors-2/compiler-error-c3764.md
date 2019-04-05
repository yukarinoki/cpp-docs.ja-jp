---
title: コンパイラ エラー C3764
ms.date: 11/04/2016
f1_keywords:
- C3764
helpviewer_keywords:
- C3764
ms.assetid: af5d254c-8d4a-4dda-aad9-3c5c1257c868
ms.openlocfilehash: 2570ee9abb148b919242de7786cd6fa91765286f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773581"
---
# <a name="compiler-error-c3764"></a>コンパイラ エラー C3764

'override_function': 基底クラス メソッド 'base_class_function' をオーバーライドすることはできません

正しくない形式のオーバーライドが検出されました。 たとえば、基底クラスの関数が`virtual`します。 詳細については、次を参照してください。[オーバーライド](../../extensions/override-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3764 が生成されます。

```
// C3764.cpp
// compile with: /clr /c
public ref struct A {
   void g(int);
   virtual void h(int);
};

public ref struct B : A {
   virtual void g(int) override {}   // C3764
   virtual void h(int) override {}   // OK
};
```

## <a name="example"></a>例

C3764 基底クラスのメソッドは、両方を明示的にはときも発生し、という名前をオーバーライドします。 次の例では、C3764 が生成されます。

```
// C3764_b.cpp
// compile with: /clr /c
ref struct A {
   virtual void Test() {}
};

ref struct B : public A {
   virtual void Test() override {}
   virtual void Test2() = A::Test {}   // C3764
};
```