---
description: 詳細については、「コンパイラエラー C3668」を参照してください。
title: コンパイラ エラー C3668
ms.date: 11/04/2016
f1_keywords:
- C3668
helpviewer_keywords:
- C3668
ms.assetid: 53a96698-bde4-4447-95b5-b5108291f60c
ms.openlocfilehash: a13de2f8ea1ca9c8bf6d66483c777d74675fef9e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97269498"
---
# <a name="compiler-error-c3668"></a>コンパイラ エラー C3668

' method ': オーバーライド指定子 ' override ' を持つメソッドは、基底クラスのメソッドをオーバーライドしませんでした

関数が存在しない関数をオーバーライドしようとしました。

詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では、C3668 が生成されます。

```cpp
// C3668.cpp
// compile with: /c
__interface I {
   void f(int);   // virtual by default
};

class J {
public:
   void g(int);
   virtual void h(int);
};

struct R : I,J {
   virtual void f() override {}   // C3668
   virtual void f(int) override {}   // OK

   virtual void g(int) override {}   // C3668
   virtual void h(int) override {}   // OK
};
```
