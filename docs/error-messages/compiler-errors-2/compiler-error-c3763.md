---
title: コンパイラ エラー C3763
ms.date: 11/04/2016
f1_keywords:
- C3763
helpviewer_keywords:
- C3763
ms.assetid: 58b1f079-cd1d-46e0-9431-ea18210106b7
ms.openlocfilehash: 7ccb3d846982bbf9a52a7267549f6481b5a1bd9b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503965"
---
# <a name="compiler-error-c3763"></a>コンパイラ エラー C3763

' type ': ' retval ' および ' out ' はデータポインター型でのみ使用できます

[Out](../../windows/attributes/out-cpp.md)または[retval](../../windows/attributes/retval.md)属性は、pointer 型のパラメーターでのみ使用できます。 属性を削除するか、または pointer 型のパラメーターを作成してください。

次の例では、C3763 が生成されます。

```cpp
// C3763.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlplus.h>
#include <atlcom.h>

[ module(name=test) ];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IF84 : IDispatch
{
   [id(0x00000002)]HRESULT m2([out]unsigned char);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002") ]
class CF84 : public IF84
{   // C3763
public:
   HRESULT __stdcall m2(unsigned char i)
   {
      return S_OK;
   }
};

int main()
{
}
```
