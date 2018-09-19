---
title: コンパイラ エラー C3703 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3703
dev_langs:
- C++
helpviewer_keywords:
- C3703
ms.assetid: 7e3677d9-f2be-4c26-998f-423564e9023c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 730409d9db313294e23693b6d50d4b0aff0f8869
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46043886"
---
# <a name="compiler-error-c3703"></a>コンパイラ エラー C3703

'イベント ハンドラー': イベント ハンドラー メソッドでは、ソース 'event' として同じストレージ クラスがあります

[イベント](../../cpp/event-handling.md)はイベント ハンドラーがフックされているよりも、別のストレージ クラスがあります。 たとえば、このエラーは、イベント ハンドラーは静的メンバー関数であり、イベントが静的でない場合に発生します。 このエラーを解決するには、イベントとイベント ハンドラーと同じストレージ クラスを提供します。

次の例では、C3703 が生成されます。

```
// C3703.cpp
// C3703 expected
#include <stdio.h>

[event_source(type=native)]
class CEventSrc {
public:
   __event static void MyEvent();
};

[event_receiver(type=native)]
class CEventHandler {
public:
   // delete the following line to resolve
   void MyHandler() {}

   // try the following line instead
   // static void MyHandler() {}

   void HookIt(CEventSrc* pSource) {
      __hook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);
   }

   void UnhookIt(CEventSrc* pSource) {
      __unhook(CEventSrc::MyEvent, pSource, &CEventHandler::MyHandler);
   }
};

int main() {
   CEventSrc src;
   CEventHandler hnd;

   hnd.HookIt(&src);
   __raise src.MyEvent();
   hnd.UnhookIt(&src);
}
```