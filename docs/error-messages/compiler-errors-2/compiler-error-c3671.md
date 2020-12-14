---
description: 詳細については、「コンパイラエラー C3671」を参照してください。
title: コンパイラ エラー C3671
ms.date: 11/04/2016
f1_keywords:
- C3671
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
ms.openlocfilehash: a8fba0ccec84789b7fe5e45cd72b18abc3fe63b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228873"
---
# <a name="compiler-error-c3671"></a>コンパイラ エラー C3671

' function_1 ': 関数は ' function_2 ' をオーバーライドしません

明示的なオーバーライド構文を使用する場合、関数がオーバーライドされないと、コンパイラはエラーを生成します。  詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

次の例では、C3671 が生成されます。

```cpp
// C3671.cpp
// compile with: /clr /c
ref struct S {
   virtual void f();
};

ref struct S1 : S {
   virtual void f(int) new sealed = S::f;   // C3671
   virtual void f() new sealed = S::f;
};
```
