---
title: コンパイラ エラー C3911
ms.date: 11/04/2016
f1_keywords:
- C3911
helpviewer_keywords:
- C3911
ms.assetid: b786da59-0e99-479d-bc0d-551126e940f2
ms.openlocfilehash: 25bf8def4e0a8085e20dc6ba9a04dc7f27cee651
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775986"
---
# <a name="compiler-error-c3911"></a>コンパイラ エラー C3911

'event_accessor_method': 関数は、型 'signature' をいる必要があります

イベントのアクセサー メソッドが適切に宣言されていません。

詳細については、次を参照してください。[イベント](../../extensions/event-cpp-component-extensions.md)します。

次の例では、C3911 が生成されます。

```
// C3911.cpp
// compile with: /clr
using namespace System;
delegate void H(String^, int);

ref class X {
   event H^ E1 {
      void add() {}   // C3911
      // try the following line instead
      // void add(H ^ h) {}

      void remove(){}
      // try the following line instead
      // void remove(H ^ h) {}

      void raise(){}
      // try the following line instead
      // void raise(String ^ s, int i) {}
   };
};
```