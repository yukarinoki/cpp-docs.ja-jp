---
description: 詳細については、「コンパイラエラー C3900」を参照してください。
title: コンパイラ エラー C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: 7b210eb6369b8953f36821d45690de8656113af2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97238935"
---
# <a name="compiler-error-c3900"></a>コンパイラ エラー C3900

' member ': 現在のスコープでは許可されていません

プロパティブロックには、関数宣言とインライン関数定義のみを含めることができます。 プロパティブロックでは、関数以外のメンバーは許可されません。 Typedef、演算子、または friend 関数は使用できません。 詳細については、「 [property](../../extensions/property-cpp-component-extensions.md)」を参照してください。

イベント定義には、アクセスメソッドと関数のみを含めることができます。

次の例では、C3900 が生成されます。

```cpp
// C3900.cpp
// compile with: /clr
ref class X {
   property int P {
      void set(int);   // OK
      int i;   // C3900 variable declaration
   };
};
```

次の例では、C3900 が生成されます。

```cpp
// C3900b.cpp
// compile with: /clr
using namespace System;
delegate void H();
ref class X {
   event H^ E {
      int m;   // C3900

      // OK
      void Test() {}

      void add( H^ h ) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```
