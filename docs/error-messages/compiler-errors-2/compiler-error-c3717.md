---
description: 詳細については、「コンパイラエラー C3717」を参照してください。
title: コンパイラ エラー C3717
ms.date: 11/04/2016
f1_keywords:
- C3717
helpviewer_keywords:
- C3717
ms.assetid: ae4fceb1-2583-4577-b2f1-40971a017055
ms.openlocfilehash: fecd417af1eceb40ef8b8e48fda40b3ec5e5b36a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189432"
---
# <a name="compiler-error-c3717"></a>コンパイラ エラー C3717

' method ': イベントを発生させるメソッドを定義することはできません

実装を含むイベントメソッドを宣言しました。 [__Event](../../cpp/event.md)メソッドの宣言に定義を含めることはできません。 このエラーを修正するには、イベントメソッドの宣言に定義がないことを確認します。 たとえば、次のコードでは、コメントで示されているように、関数本体を宣言から削除し `event1` ます。

次の例では、C3717 が生成されます。

```cpp
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
