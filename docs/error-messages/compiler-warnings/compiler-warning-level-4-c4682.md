---
title: コンパイラの警告 (レベル 4) C4682
ms.date: 11/04/2016
f1_keywords:
- C4682
helpviewer_keywords:
- C4682
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
ms.openlocfilehash: 6566c27999f218b7a214e32dde96bd1cf96fbb12
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653064"
---
# <a name="compiler-warning-level-4-c4682"></a>コンパイラの警告 (レベル 4) C4682

'parameter': 方向性のあるパラメーター属性が指定されていません。[in] を既定とします

属性付きインターフェイスのパラメーターのメソッドに、方向属性 [in](../../windows/in-cpp.md) または [out](../../windows/out-cpp.md)が指定されていません。パラメーターの既定値は in です。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では C4682 警告が生成されます。

```
// C4682.cpp
// compile with: /W4
#pragma warning(default : 4682)
#include <windows.h>
[module(name="MyModule")];

[ library_block, object, uuid("c54ad59d-d516-41dd-9acd-afda17565c2b") ]
__interface IMyIface : IUnknown
{
   HRESULT f1(int i, int *pi); // C4682
   // try the following line
   // HRESULT f1([in] int i, [in] int *pi);
};

int main()
{
}
```