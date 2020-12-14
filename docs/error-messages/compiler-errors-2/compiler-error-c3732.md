---
description: 詳細については、「コンパイラエラー C3732」を参照してください。
title: コンパイラ エラー C3732
ms.date: 11/04/2016
f1_keywords:
- C3732
helpviewer_keywords:
- C3732
ms.assetid: 2d55a7e1-9c39-4379-a093-2f7beb27e2ca
ms.openlocfilehash: 406acf356ee0bec09eb5d9e218114256f9c58858
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245058"
---
# <a name="compiler-error-c3732"></a>コンパイラ エラー C3732

' interface ': COM イベントを発生させるカスタムインターフェイスは IDispatch から継承できません

COM イベントをサポートするインターフェイスは、から継承できません `IDispatch` 。 詳細については、「 [COM でのイベント処理](../../cpp/event-handling-in-com.md)」を参照してください。

次のエラーが発生すると、C3732 が生成されます。

```cpp
// C3732.cpp
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[module(name="test")];

// to resolve this C3732, use dual instead of object
// or inherit from IUnknown
[ object ]
__interface I : IDispatch
{
};

[ event_source(com), coclass ]
struct A
{
   __event __interface I;   // C3732
};

int main()
{
}
```
