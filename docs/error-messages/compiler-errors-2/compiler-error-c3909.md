---
title: コンパイラ エラー C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: 95de97a27fc42e98247675b1b48325593ff3c21e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406523"
---
# <a name="compiler-error-c3909"></a>コンパイラ エラー C3909

aWinRT またはマネージ イベント宣言は WinRT またはマネージ型で発生する必要があります。

Windows ランタイム イベントまたはマネージド イベントがネイティブ型内で宣言されました。 このエラーを修正するには、Windows ランタイム型またはマネージド型内でイベントを宣言します。

詳細については、次を参照してください。[イベント](../../extensions/event-cpp-component-extensions.md)します。

次の例では、C3909 を生成し、その修正方法を示しています。

```
// C3909.cpp
// compile with: /clr /c
delegate void H();
class X {
   event H^ E;   // C3909 - use ref class X instead
};

ref class Y {
   static event H^ E {
      void add(H^) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```