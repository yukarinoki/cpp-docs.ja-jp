---
title: コンパイラ エラー C3724
ms.date: 11/04/2016
f1_keywords:
- C3724
helpviewer_keywords:
- C3724
ms.assetid: cab8aba7-14fc-406f-8cc6-32744c8f31c1
ms.openlocfilehash: 126317d78785b14f5ef613ec0c83d3e50b825d60
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676123"
---
# <a name="compiler-error-c3724"></a>コンパイラ エラー C3724

必要があります #include \<windows.h > を使用すると、イベントのマルチ スレッド

使用する場合は、windows.h ファイルが必要なイベントでマルチ スレッドです。 このエラーを修正するには追加`#include <windows.h>`受信者を定義するイベント ソースとイベント内のファイルの先頭にします。

```
// C3724.cpp
// uncomment the following line to resolve
// #include <windows.h>

[event_source(native), threading(apartment)]
class CEventSrc {
public:
   __event void event1();   // C3724
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