---
title: コンパイラ エラー C3704
ms.date: 11/04/2016
f1_keywords:
- C3704
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
ms.openlocfilehash: 4e26742de6c294018f81c6f49c1719fdb11d5149
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467112"
---
# <a name="compiler-error-c3704"></a>コンパイラ エラー C3704

'function': vararg メソッドは、イベントを発生させることはできません

使用しようとする[_ _event](../../cpp/event.md) vararg メソッドにします。 このエラーを修正するのには、置換、`fireEvent(int i, ...)`呼び出しが、`fireEvent(int i)`の次のコード サンプルに示すように呼び出します。

次の例では、C3704 が生成されます。

```
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