---
description: 詳細については、「コンパイラエラー C3708」を参照してください。
title: コンパイラ エラー C3708
ms.date: 11/04/2016
f1_keywords:
- C3708
helpviewer_keywords:
- C3708
ms.assetid: 45e71564-9c7f-437f-98d8-a735ce162ed0
ms.openlocfilehash: e70bf90fb1ee8c05fd9c51fc18d024773e20774d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241808"
---
# <a name="compiler-error-c3708"></a>コンパイラ エラー C3708

' interface ': ' keyword ' の使用法が正しくありません。互換性のあるイベントソースのメンバーである必要があります

イベントとしてインターフェイスを宣言するには、イベントの宣言がイベントソースに含まれている必要があります。

次の例では、C3708 が生成されます。

```cpp
// C3708.cpp
// compile with: /c
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[ module(name="MyLibrary")];

[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface I {
   HRESULT func();
};

[ object, uuid("00000000-0000-0000-0000-000000000002") ]
__interface II {
   HRESULT func();
};

__event __interface I;   // C3708

// put the event in an event source
[ coclass, event_source(com), uuid("00000000-0000-0000-0000-000000000003") ]
struct E : II {
   __event __interface II;
};
```
