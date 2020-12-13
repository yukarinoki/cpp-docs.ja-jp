---
description: '詳細情報: コンパイラの警告 (レベル 4) C4682'
title: コンパイラの警告 (レベル 4) C4682
ms.date: 11/04/2016
f1_keywords:
- C4682
helpviewer_keywords:
- C4682
ms.assetid: 858ea157-1244-4a61-85df-97b3de43d418
ms.openlocfilehash: c91b1b7f1ac378faa7032bbc9e8c508124773c6c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97133839"
---
# <a name="compiler-warning-level-4-c4682"></a>コンパイラの警告 (レベル 4) C4682

'parameter': 方向性のあるパラメーター属性が指定されていません。[in] を既定とします

属性付きインターフェイスのパラメーターのメソッドに、方向属性の1つ ( [in](../../windows/attributes/in-cpp.md) または [out](../../windows/attributes/out-cpp.md)) がありません。パラメーターの既定値は in です。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では C4682 警告が生成されます。

```cpp
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
