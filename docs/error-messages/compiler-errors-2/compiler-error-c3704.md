---
description: 詳細については、「コンパイラエラー C3704」を参照してください。
title: コンパイラ エラー C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: aae489b2d8657a1e62adc654d148be6cd0403af1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278182"
---
# <a name="compiler-error-c3704"></a>コンパイラ エラー C3704

' function ': vararg メソッドはイベントを発生させることができません

Vararg メソッドで [__event](../../cpp/event.md) を使用しようとしました。 このエラーを解決するには、 `fireEvent(int i, ...)` 次の `fireEvent(int i)` コードサンプルに示すように、呼び出しを呼び出しに置き換えます。

次の例では、C3704 が生成されます。

```cpp
// C3704.cpp
[ event_source(native) ]
class CEventSrc {
   public:
      __event void fireEvent(int i, ...);   // C3704
      // try the following line instead:
      // __event void fireEvent(int i);
};

int main() {
}
```
