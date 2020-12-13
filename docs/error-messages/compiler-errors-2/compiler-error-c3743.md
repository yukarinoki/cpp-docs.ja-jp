---
description: 詳細については、「コンパイラエラー C3743」を参照してください。
title: コンパイラ エラー C3743
ms.date: 11/04/2016
f1_keywords:
- C3743
helpviewer_keywords:
- C3743
ms.assetid: 7ca9a76e-7b60-46d1-ab8b-18600cf1a306
ms.openlocfilehash: 1afad204f25220df53d58313a5742424e3491710
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340243"
---
# <a name="compiler-error-c3743"></a>コンパイラ エラー C3743

event_receiver の ' layout_dependent ' パラメーターが true の場合にのみ、インターフェイス全体をフック/アンフックできます

[__Unhook](../../cpp/unhook.md)関数は、event_receiver クラスのパラメーターに渡される値に基づいて、取得するパラメーターの数が異なり `layout_dependent` ます。 [](../../windows/attributes/event-receiver.md)

次の例では、C3743 が生成されます。

```cpp
// C3743.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[module(name="xx")];
[object] __interface I { HRESULT f(); };

[event_receiver(com, layout_dependent=true), coclass]
struct R : I {
        HRESULT f() {
      return 0;
   }
        R() {
   }

   R(I* a) {
      __hook(I, a, &R::f);   // C3743
      // The following line resolves the error.
      // __hook(I, a);
   }
};
```
