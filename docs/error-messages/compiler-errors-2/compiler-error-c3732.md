---
title: コンパイラ エラー C3732
ms.date: 11/04/2016
f1_keywords:
- C3732
helpviewer_keywords:
- C3732
ms.assetid: 2d55a7e1-9c39-4379-a093-2f7beb27e2ca
ms.openlocfilehash: c71cca3643f6337060de6e4bb56ac64d8f0d6e4e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327991"
---
# <a name="compiler-error-c3732"></a>コンパイラ エラー C3732

'interface': COM イベントを発生させるカスタム インターフェースは IDispatch から継承できません

COM イベントをサポートするインターフェイスを継承できません`IDispatch`します。 詳細については、次を参照してください。 [COM でのイベント処理](../../cpp/event-handling-in-com.md)します。

次のエラー C3732 が生成されます。

```
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