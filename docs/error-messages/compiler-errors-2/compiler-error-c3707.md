---
description: 詳細については、「コンパイラエラー C3707」を参照してください。
title: コンパイラ エラー C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: 77a1193eae9b9d0158065978438b5af1d2176d12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241847"
---
# <a name="compiler-error-c3707"></a>コンパイラ エラー C3707

' function ': ディスパッチインターフェイスには dispid が必要です

メソッドを使用する場合は、 `dispinterface` メソッドを割り当てる必要があり `dispid` ます。 このエラーを解決するには、 `dispid` メソッドにを割り当て `dispinterface` ます。たとえば、次のサンプルでは、メソッドの属性をコメント解除し `id` ます。 詳細については、「属性の [ディスパッチインターフェイス](../../windows/attributes/dispinterface.md) と [id](../../windows/attributes/id.md)」を参照してください。

次の例では、C3707 が生成されます。

```cpp
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
