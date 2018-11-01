---
title: コンパイラ エラー C3701
ms.date: 11/04/2016
f1_keywords:
- C3701
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
ms.openlocfilehash: 2efbf3c48b7c366d262facac9cebb4f72d9f1513
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580600"
---
# <a name="compiler-error-c3701"></a>コンパイラ エラー C3701

'function': イベント ソースにイベントがありません

使用しようとする[event_source](../../windows/event-source.md)をイベント メソッドを持たないクラスにします。 このエラーを修正するには、クラスに 1 つまたは複数のイベントを追加します。

次の例では、C3701 が生成されます。

```
// C3701.cpp
[ event_source(native) ]
class CEventSrc {
public:
   // uncomment the following line to resolve this C3701
   // __event void fireEvent(int i);
};   // C3701

int main() {
}
```