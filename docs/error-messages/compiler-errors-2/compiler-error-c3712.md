---
description: 詳細については、「コンパイラエラー C3712」を参照してください。
title: コンパイラ エラー C3712
ms.date: 11/04/2016
f1_keywords:
- C3712
helpviewer_keywords:
- C3712
ms.assetid: 65b1fcaf-be89-4c55-9e40-25ec03457253
ms.openlocfilehash: 530666d72ff72abef1286d594922dc877907b4e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241665"
---
# <a name="compiler-error-c3712"></a>コンパイラ エラー C3712

' method ': イベントハンドラーメソッドは、ソース ' method ' と同じ型を返す必要があります

イベントハンドラーメソッドを定義しましたが、これはソースイベントメソッドと同じ型を返しませんでした。 このエラーを解決するには、イベントハンドラーメソッドに、ソースイベントメソッドと同じ戻り値の型を指定します。

次の例では、C3712 が生成されます。

```cpp
// C3712.cpp
// compile with: /c
[event_source(native)]
class CEventSrc {
public:
   __event void event1();
};

[event_receiver(native)]
class CEventRec {
public:
   int handler1() { return 0; }
   // try the following line instead
   // void handler1() {}

   void HookEvents(CEventSrc* pSrc) {
      __hook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
   void UnhookEvents(CEventSrc* pSrc) {
      __unhook(&CEventSrc::event1, pSrc, &CEventRec::handler1);   // C3712
   }
};
```
