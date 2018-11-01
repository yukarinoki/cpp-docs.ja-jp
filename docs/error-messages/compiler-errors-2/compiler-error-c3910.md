---
title: コンパイラ エラー C3910
ms.date: 11/04/2016
f1_keywords:
- C3910
helpviewer_keywords:
- C3910
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
ms.openlocfilehash: b9194149c532044f6c8a1eab84729f7896f1352b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568546"
---
# <a name="compiler-error-c3910"></a>コンパイラ エラー C3910

'event': メンバー 'method' を定義する必要があります

イベントが定義されましたが、アクセサーを指定すると、必要なメソッドが含まれていませんでした。

詳細については、次を参照してください。[イベント](../../windows/event-cpp-component-extensions.md)します。

次の例では、C3910 が生成されます。

```
// C3910.cpp
// compile with: /clr /c
delegate void H();
ref class X {
   event H^ E {
      // uncomment the following lines
      // void add(H^) {}
      // void remove( H^ h ) {}
      // void raise( ) {}
   };   // C3910

   event H^ E2; // OK data member
};
```