---
title: コンパイラ エラー C3717
ms.date: 11/04/2016
f1_keywords:
- C3717
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
ms.openlocfilehash: f7e60b4f1b6a1337ef93088e4f36ce2a1b34dc47
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599306"
---
# <a name="compiler-error-c3717"></a>コンパイラ エラー C3717

'method': イベントを発生させるメソッドを定義することはできません

実装を含むイベント メソッドが宣言されています。 [_ _Event](../../cpp/event.md)メソッドの宣言は定義を持つことはできません。 このエラーを解決するには、定義を持つイベントのメソッド宣言がないことを確認します。 たとえば、次のコードから関数の本体を削除、`event1`宣言のコメントで示されます。

次の例では、C3717 が生成されます。

```
// C3717.cpp
[event_source(native)]
class CEventSrc {
public:
   __event void event1() {   // C3717
   }

   // remove definition for event1 and substitute following declaration
   // __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   void handler1() {
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