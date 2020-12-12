---
description: 詳細については、「コンパイラエラー C3653」を参照してください。
title: コンパイラ エラー C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: 6f41d52416d2fee05873197efa60e4b888cf29f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320106"
---
# <a name="compiler-error-c3653"></a>コンパイラ エラー C3653

' function ': 名前付きオーバーライドとして使用することはできません。オーバーライドされる関数が見つかりません。:: 演算子を使用して、関数に明示的に名前を指定しましたか?

明示的なオーバーライドで、インターフェイスで見つからなかった関数が指定されました。 詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

次の例では、C3653 が生成されます。

```cpp
// C3653.cpp
// compile with: /clr
public interface struct I {
   void h();
};

public ref struct X : public I {
   virtual void f() new sealed = J {};   // C3653 no J in scope
   virtual void g() {}   // OK
   virtual void h() new sealed = I::h {};   // OK
};
```
