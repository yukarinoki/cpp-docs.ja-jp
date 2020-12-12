---
description: 詳細については、「コンパイラエラー C3701」を参照してください。
title: コンパイラ エラー C3701
ms.date: 11/04/2016
f1_keywords:
- C3701
helpviewer_keywords:
- C3701
ms.assetid: a7faaa87-d2f5-4d6a-9a2f-5cab2d24a648
ms.openlocfilehash: 8ebc8ac41091770a59876fb829d86997d7f5709c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228691"
---
# <a name="compiler-error-c3701"></a>コンパイラ エラー C3701

' function ': event_source にイベントがありません

イベントメソッドのないクラスで [event_source](../../windows/attributes/event-source.md) を使用しようとしました。 このエラーを解決するには、クラスに1つ以上のイベントを追加します。

次の例では、C3701 が生成されます。

```cpp
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
