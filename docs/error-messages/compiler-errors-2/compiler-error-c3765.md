---
description: 詳細については、「コンパイラエラー C3765」を参照してください。
title: コンパイラ エラー C3765
ms.date: 11/04/2016
f1_keywords:
- C3765
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
ms.openlocfilehash: 29de872030143ab33e1349f07ac3b81cb841e113
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234619"
---
# <a name="compiler-error-c3765"></a>コンパイラ エラー C3765

' event ': event_receiver としてマークされたクラス/構造体 ' type ' でイベントを定義することはできません

クラスが [event_receiver](../../windows/attributes/event-receiver.md) 属性でマークされている場合、クラスに [__event](../../cpp/event.md) 宣言を含めることはできません。

次の例では、C3765 が生成されます。

```cpp
// C3765.cpp
[event_receiver(native)]
struct ER2 {
   __event void f();   // C3765
   __event void b(int);   // C3765
};
```
