---
description: 詳細については、「コンパイラエラー C3651」を参照してください。
title: コンパイラ エラー C3651
ms.date: 11/04/2016
f1_keywords:
- C3651
helpviewer_keywords:
- C3651
ms.assetid: a03e692e-c219-4654-9827-8415cfa5a22d
ms.openlocfilehash: 03845059c1c99db7a228d2678148f768cb2e2c1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203719"
---
# <a name="compiler-error-c3651"></a>コンパイラ エラー C3651

' member ': 明示的なオーバーライドとして使用することはできません。基底クラスのメンバーである必要があります

明示的なオーバーライドが指定されましたが、オーバーライドされている関数は基本型ではない型に含まれていました。

詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

次の例では、C3651 が生成されます。

```cpp
// C3651.cpp
// compile with: /clr /c
ref class C {
public:
   virtual void func2();
};

ref class Other {
public:
   virtual void func();
};

ref class D : public C {
public:
   virtual void func() new sealed = Other::func;   // C3651
   virtual void func2() new sealed = C::func2;   // OK
};
```
