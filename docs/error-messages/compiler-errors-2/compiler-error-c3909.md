---
description: 詳細については、「コンパイラエラー C3909」を参照してください。
title: コンパイラ エラー C3909
ms.date: 11/04/2016
f1_keywords:
- C3909
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
ms.openlocfilehash: a85e0201e192caae1e4f170a12544177cbb2d7f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144158"
---
# <a name="compiler-error-c3909"></a>コンパイラ エラー C3909

aWinRT またはマネージイベントの宣言は、WinRT またはマネージ型で発生する必要があります

Windows ランタイム イベントまたはマネージド イベントがネイティブ型内で宣言されました。 このエラーを修正するには、Windows ランタイム型またはマネージド型内でイベントを宣言します。

詳細については、「 [event](../../extensions/event-cpp-component-extensions.md)」を参照してください。

次の例では、C3909 を生成し、その修正方法を示しています。

```cpp
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
