---
title: コンパイラ エラー C3765 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3765
dev_langs:
- C++
helpviewer_keywords:
- C3765
ms.assetid: feadee7a-fcfb-402c-af2f-0e656f814a13
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cac3930e4f5ec42587a9f557adc7a82d750b3819
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042131"
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