---
description: 詳細については、「コンパイラエラー C3711」を参照してください。
title: コンパイラ エラー C3711
ms.date: 11/04/2016
f1_keywords:
- C3711
helpviewer_keywords:
- C3711
ms.assetid: 26d581cc-2153-4ee0-b814-a371184be3e1
ms.openlocfilehash: 5ced0d5e83c149f3634053680aa52821e0d9bbe8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241691"
---
# <a name="compiler-error-c3711"></a>コンパイラ エラー C3711

' method ': マネージドでないイベントソースメソッドは、void または整数型を返さなければなりません

Void または整数型を返さないイベントソースのメソッドを定義しました。 このエラーを修正するには、イベントおよびイベントハンドラーの戻り値の型がである **`void`** か、またはなどの整数型であることを確認し **`int`** **`long`** ます。

次の例では、C3711 が生成されます。

```cpp
// C3711.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[event_source(native)]
class CEventSrc {
public:
   __event float event1();   // C3711
   // try the following line instead
   // __event int event1();
   // also change the handler, below
};

[event_receiver(native)]
class CEventRec {
public:
   float handler1() {         // change float to int
      return 0.0;             // change 0.0 to 0
   }
   void HookEvents(CEventSrc* pSrc) {
      __hook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};

int main() {
}
```
