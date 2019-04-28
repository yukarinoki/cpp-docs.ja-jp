---
title: コンパイラ エラー C3653
ms.date: 11/04/2016
f1_keywords:
- C3653
helpviewer_keywords:
- C3653
ms.assetid: 316549d7-f7ef-4578-a2ba-57adc8aac527
ms.openlocfilehash: 75e2c061190b24019491db7a625ecafb5ac82b6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62227514"
---
# <a name="compiler-error-c3653"></a>コンパイラ エラー C3653

'function': 名前付きオーバーライドとして使用できません: が見つかりませんオーバーライドされる関数。関数の明示的に名前を使用してください、:: 演算子でしょうか。

明示的なオーバーライドでは、任意のインターフェイスに見つからなかった関数が指定します。 詳細については、次を参照してください。[明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)します。

次の例では、C3653 が生成されます。

```
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