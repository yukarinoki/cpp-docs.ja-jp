---
description: '詳細情報: コンパイラの警告 (レベル 4) C4680'
title: コンパイラの警告 (レベル 4) C4680
ms.date: 11/04/2016
f1_keywords:
- C4680
helpviewer_keywords:
- C4680
ms.assetid: 6e043f4c-c601-4b77-8130-920cff1d912e
ms.openlocfilehash: 85f14273efb2b7d91a6b663e69918b77bcb7c597
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133875"
---
# <a name="compiler-warning-level-4-c4680"></a>コンパイラの警告 (レベル 4) C4680

' class ': コクラスは既定のインターフェイスを指定していません

[コクラス](../../windows/attributes/coclass.md)属性でマークされたクラスの[既定](../../windows/attributes/default-cpp.md)のインターフェイスが指定されませんでした。 オブジェクトを使用するためには、インターフェイスを実装する必要があります。

次の例では、C4680 が生成されます。

```cpp
// C4680.cpp
// compile with: /W4
#include <windows.h>
[module(name="MyModule")];

[ object, uuid(373a1a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface1
{
   HRESULT f1();
};

[ object, uuid(37331a4c-469b-11d3-a6b0-00c04f79ae8f) ]
__interface IMyIface2
{
   HRESULT f1();
};

// to resolve C4680, specify a source interface also
// for example, default(IMyIface1, IMyface2)
[ coclass, uuid(373a1a4d-469b-11d3-a6b0-00c04f79ae8f), default(IMyIface1), source(IMyIface1) ]
class CMyClass : public IMyIface1
{   // C4680
};

int main()
{
}
```
