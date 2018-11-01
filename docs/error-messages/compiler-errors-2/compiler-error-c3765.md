---
title: コンパイラ エラー C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 86c043889c5342ed4f3edfc4d8a298bcbd345b3b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456395"
---
# <a name="compiler-error-c3765"></a>コンパイラ エラー C3765

'event': event_receiver 'の type' マーク クラス/構造体でイベントを定義することはできません

クラスが付いている場合、 [event_receiver](../../windows/event-receiver.md)クラスに含めることはできません、属性、 [_ _event](../../cpp/event.md)宣言します。

次の例では、C3765 が生成されます。

```
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```