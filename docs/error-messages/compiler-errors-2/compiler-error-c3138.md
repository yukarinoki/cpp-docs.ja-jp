---
title: コンパイラエラー C3138
ms.date: 11/04/2016
f1_keywords:
- C3138
helpviewer_keywords:
- C3138
ms.assetid: 364ee9e8-9358-410e-bd35-9c4a226a3753
ms.openlocfilehash: aca5c78c07852317308427d935eef5942523512b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91501398"
---
# <a name="compiler-error-c3138"></a>コンパイラエラー C3138

' interface ': ' attribute ' インターフェイスは IDispatch、または IDispatch から継承したインターフェイスから継承する必要があります

[デュアル](../../windows/attributes/dual.md)または[ディスパッチ](../../windows/attributes/dispinterface.md)インターフェイスの属性を持つインターフェイスは、 `IDispatch` 直接または間接の基本インターフェイスとして持っていません。

次の例では、C3138 が生成されます。

```cpp
// C3138.cpp
#include <unknwn.h>

[ object, uuid("77ac9240-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyCustomInterface
{
   HRESULT mf1(void);
};

[ dispinterface, uuid("3536f8a0-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDispInterface : IUnknown
{
   [id(1)] HRESULT mf2(void);
};

[ object, dual, uuid("34e90a10-6e9a-11d2-97de-0000f805d73b") ]
__interface IMyDualInterface : IMyCustomInterface  // C3138 expected
{
   HRESULT mf3(void);
};
```
