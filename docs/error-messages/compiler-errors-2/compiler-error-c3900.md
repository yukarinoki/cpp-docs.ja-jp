---
title: コンパイラ エラー C3900
ms.date: 11/04/2016
f1_keywords:
- C3900
helpviewer_keywords:
- C3900
ms.assetid: a94cc561-8fa8-4344-9e01-e81ff462fae5
ms.openlocfilehash: d031b55407d108b4f8be362156911bfae688326a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512360"
---
# <a name="compiler-error-c3900"></a>コンパイラ エラー C3900

'member': 現在のスコープで許可されていません

プロパティ ブロックは、関数の宣言とインライン関数定義だけに含めることができます。 プロパティ ブロックでは、関数以外のメンバーは許可されません。 Typedef、演算子、またはフレンド関数は許可されません。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md)」を参照してください。

イベントの定義には、アクセス方法と関数のみを含めることができます。

次の例では、C3900 が生成されます。

```
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

```
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