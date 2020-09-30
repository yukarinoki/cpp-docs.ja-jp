---
title: コンパイラ エラー C3707
ms.date: 11/04/2016
f1_keywords:
- C3707
helpviewer_keywords:
- C3707
ms.assetid: ac63a5dd-7a4b-48d2-9f2a-be9cb090134c
ms.openlocfilehash: a09bf080c72e154a37cec5cdb75e714c12dd7150
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507974"
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
