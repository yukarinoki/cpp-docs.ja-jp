---
title: コンパイラ エラー C3704 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3704
dev_langs:
- C++
helpviewer_keywords:
- C3704
ms.assetid: ee40ea35-a214-4dec-9489-d7f155dd0ac2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4504534e3a53f37089f0b0ba045b7afde5a8065d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054988"
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