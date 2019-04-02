---
title: コンパイラ エラー C3671
ms.date: 11/04/2016
f1_keywords:
- C3671
helpviewer_keywords:
- C3671
ms.assetid: d684e4ae-87e2-4424-80bb-6f346652c831
ms.openlocfilehash: c4534b11f3aedf638f69337fb6a7af778e086bb4
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778989"
---
# <a name="compiler-error-c3671"></a>コンパイラ エラー C3671

'function_1' : function does not override 'function_2'

明示的なオーバーライド構文を使用する場合、コンパイラは、関数がオーバーライドされていない場合、エラーを生成します。  参照してください[明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)詳細についてはします。

## <a name="example"></a>例

次の例では、C3671 が生成されます。

```
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