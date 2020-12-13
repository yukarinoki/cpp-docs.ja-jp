---
description: 詳細については、「コンパイラエラー C3741」を参照してください。
title: コンパイラ エラー C3741
ms.date: 11/04/2016
f1_keywords:
- C3741
helpviewer_keywords:
- C3741
ms.assetid: ed311315-cc32-49c9-97fa-01b293d81526
ms.openlocfilehash: 158555995449416da23120cafe16262cbb1a6208
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340256"
---
# <a name="compiler-error-c3741"></a>コンパイラ エラー C3741

' class ': event_receiver = true の ' layout_dependent ' パラメーターが指定されている場合、コクラスでなければなりません

`layout_dependent=true` [Event_receiver](../../windows/attributes/event-receiver.md)クラスの場合は、クラスに[コクラス](../../windows/attributes/coclass.md)属性も指定する必要があります。

次の例では、C3741 が生成されます。

```cpp
// C3741.cpp
// compile with: /c
// C3741 expected
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[module(name="xx")];

[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface I{ HRESULT f(); };

// Delete the following line to resolve.
[ event_receiver(com, layout_dependent=true)]

// class or struct must be declared with coclass
// Uncomment the following line to resolve.
// [ event_receiver(com, layout_dependent=true), coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct R : I {
   HRESULT f(){ return 0; }
   R(){}
   R(I* a){ __hook(I, a); }
};
```
