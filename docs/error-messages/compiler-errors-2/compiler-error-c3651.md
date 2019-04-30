---
title: コンパイラ エラー C3651
ms.date: 11/04/2016
f1_keywords:
- C3651
helpviewer_keywords:
- C3651
ms.assetid: a03e692e-c219-4654-9827-8415cfa5a22d
ms.openlocfilehash: 6e773201e3bc9a4edb1ee77f1ddcd555e0ae0c0e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388684"
---
# <a name="compiler-error-c3651"></a>コンパイラ エラー C3651

'member': 明示的なオーバーライドとして使用することはできません、基底クラスのメンバーである必要があります

明示的なオーバーライドが指定されましたが、基本データ型ではない型がオーバーライドされる関数。

詳細については、次を参照してください。[明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)します。

次の例では、C3651 が生成されます。

```
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