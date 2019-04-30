---
title: コンパイラ エラー C3919
ms.date: 11/04/2016
f1_keywords:
- C3919
helpviewer_keywords:
- C3919
ms.assetid: 5f8eddda-d751-478b-930d-e18f7191ddfb
ms.openlocfilehash: 05ac2fc9258a078f352b6012e64e86fe4b70c3f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386578"
---
# <a name="compiler-error-c3919"></a>コンパイラ エラー C3919

'event_method': 関数は型 'type' が必要

イベントのアクセサー メソッドを正しく宣言されませんでした。

イベントの詳細については、次を参照してください。[イベント](../../extensions/event-cpp-component-extensions.md)します。

次の例では、C3919 が生成されます。

```
// C3919.cpp
// compile with: /clr /c
using namespace System;
delegate void D(String^);
ref class R {
   event D^ e {
      int add(int);   // C3919
      int remove(int);   // C3919

      void add(D^);   // OK
      void remove(D^);   // OK
   }
};
```