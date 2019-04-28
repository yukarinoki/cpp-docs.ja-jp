---
title: コンパイラ エラー C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 8a1525539c84ea427815a03057bb6d2f9213fec7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328524"
---
# <a name="compiler-error-c3707"></a>コンパイラ エラー C3707

'function': dispinterface メソッドは dispid を持つ必要があります

使用する場合、`dispinterface`メソッドを割り当てる必要がありますが、`dispid`します。 このエラーを修正するのには、割り当て、`dispid`を`dispinterface`メソッド、たとえば、コメントを解除して、`id`メソッドは、次の例の属性。 詳細については、属性を参照してください。 [dispinterface](../../windows/dispinterface.md)と[id](../../windows/id.md)します。

次の例では、C3707 が生成されます。

```
// C3707.cpp
#include <atlbase.h>
#include <atlcom.h>
#include <atlctl.h>

[module(name="xx")];
[dispinterface]
__interface IEvents : IDispatch
{
   HRESULT event1([in] int i);   // C3707
   // try the following line instead
   // [id(1)] HRESULT event1([in] int i);
};

int main() {
}
```