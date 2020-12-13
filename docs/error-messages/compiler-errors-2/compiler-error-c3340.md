---
description: 詳細については、「コンパイラエラー C3340」を参照してください。
title: コンパイラ エラー C3340
ms.date: 11/04/2016
f1_keywords:
- C3340
helpviewer_keywords:
- C3340
ms.assetid: 23b12298-b92a-4717-8380-f165c998cb8a
ms.openlocfilehash: 3c944d8d61a93fb3985e85e946f147eecd56624a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337316"
---
# <a name="compiler-error-c3340"></a>コンパイラ エラー C3340

'interface': コクラス 'class' で、インターフェイスの設定を同時に 'restricted' と 'default' にすることはできません

[restricted](../../windows/attributes/restricted.md) 属性と [default](../../windows/attributes/default-cpp.md) 属性は相互に排他的です。

次の例では C3340 が生成されます。

```cpp
// C3340.cpp
#include <windows.h>
[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface
{
   HRESULT f1();
};

[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f),
default(IMyIface),
source(IMyIface),restricted(IMyIface) ]
class CmyClass // C3340
{
};

int main()
{
}
```
