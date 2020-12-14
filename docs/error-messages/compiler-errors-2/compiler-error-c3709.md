---
description: 詳細については、「コンパイラエラー C3709」を参照してください。
title: コンパイラ エラー C3709
ms.date: 11/04/2016
f1_keywords:
- C3709
helpviewer_keywords:
- C3709
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
ms.openlocfilehash: 0c884801cc3c720df1018bf7c6d13b13465982a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241795"
---
# <a name="compiler-error-c3709"></a>コンパイラ エラー C3709

' function ': __hook/_unhook でイベントを指定するための構文が正しくありません \_

[__Hook](../../cpp/hook.md)または[__unhook](../../cpp/unhook.md)でイベントソースを指定する場合、最初のパラメーターは有効なイベントメソッドである必要があり、2番目のパラメーターは、(メソッドではなく) 有効なイベントソースオブジェクトである必要があります。

次の例では、C3709 が生成されます。

```cpp
// C3709.cpp
// compile with: /LD
[event_source(native)]
class CEventSrc
{
public:
   __event void event1();
};

[event_receiver(native)]
class CEventRec
{
public:
   void handler1()
   {
   }

   void HookEvents(CEventSrc* pSrc)
   {
      __hook(bad, pSrc, CEventRec::handler1);   // C3709
      // Try the following line instead:
      // __hook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }

   void UnhookEvents(CEventSrc* pSrc)
   {
      __unhook(&CEventSrc::event1, pSrc, CEventRec::handler1);
   }
};
```
