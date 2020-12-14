---
description: 詳細については、「コンパイラエラー C3136」を参照してください。
title: コンパイラエラー C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: 4203eaa1f41603075bbb8162b7156783c8f2680a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239377"
---
# <a name="compiler-error-c3136"></a>コンパイラエラー C3136

' interface ': COM インターフェイスは他の COM インターフェイスからのみ継承できます。 ' interface ' は COM インターフェイスではありません。

インターフェイス [属性](../../windows/attributes/interface-attributes.md) を適用したインターフェイスは、COM インターフェイスではないインターフェイスから継承されます。 COM インターフェイスは、最終的にから継承 `IUnknown` します。 インターフェイス属性が前に置かれているインターフェイスは、COM インターフェイスです。

次の例では、C3136 が生成されます。

```cpp
// C3136.cpp
#include "unknwn.h"

__interface A   // C3136
// try the following line instead
// _interface A : IUnknown
{
   int a();
};

[object]
__interface B : A
{
   int aa();
};
```
