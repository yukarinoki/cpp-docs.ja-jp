---
title: コンパイラ エラー C3709
ms.date: 11/04/2016
f1_keywords:
- C3709
helpviewer_keywords:
- C3709
ms.assetid: d5576b04-2f93-420a-8f3e-8b8e987e8dab
ms.openlocfilehash: 3eb2963916cbbcbd925f755f9162ce59e9bff569
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328433"
---
# <a name="compiler-error-c3709"></a>コンパイラ エラー C3709

'function': _ _hook でイベントを指定するための構文が正しくありません/\__unhook

持つイベント ソースを指定すると[_ _hook](../../cpp/hook.md)または[_ _unhook](../../cpp/unhook.md)最初のパラメーターは有効なイベント メソッドである必要があります、2 番目のパラメーターは有効なイベント ソース オブジェクト (メソッドではない) である必要があります。

次の例では、C3709 が生成されます。

```
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