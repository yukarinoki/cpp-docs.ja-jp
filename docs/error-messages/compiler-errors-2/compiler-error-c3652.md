---
description: 詳細については、「コンパイラエラー C3652」を参照してください。
title: コンパイラ エラー C3652
ms.date: 11/04/2016
f1_keywords:
- C3652
helpviewer_keywords:
- C3652
ms.assetid: 15d68737-177e-41f1-80e0-7c3e2afdf0fc
ms.openlocfilehash: d7ef611f58a62cd7a209ee680390c147759c9b64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203667"
---
# <a name="compiler-error-c3652"></a>コンパイラ エラー C3652

' override ': 明示的にオーバーライドする関数は仮想でなければなりません

明示的なオーバーライドを行う関数は、virtual である必要があります。 詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

次の例では、C3652 が生成されます。

```cpp
// C3652.cpp
// compile with: /clr /c
public interface class I {
   void f();
};

public ref struct R : I {
   void f() = I::f {}   // C3652
   // try the following line instead
   // virtual void f() = I::f {}
};
```
