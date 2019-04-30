---
title: コンパイラ エラー C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 86c043889c5342ed4f3edfc4d8a298bcbd345b3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400241"
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