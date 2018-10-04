---
title: コンパイラ エラー C3136 |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3136
dev_langs:
- C++
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 082a89b69092a8320f6bb4b930d01a7fd2de10c8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788384"
---
# <a name="compiler-error-c3136"></a>コンパイラ エラー C3136

'interface': COM インターフェイスは、別の COM インターフェイスからのみ継承できます、'interface' は COM インターフェイスはありません。

適用されているインターフェイス、[インターフェイス属性](../../windows/attributes/interface-attributes.md)COM インターフェイスではないインターフェイスから継承します。 COM インターフェイスが最終的に継承`IUnknown`します。 インターフェイス属性に続く任意のインターフェイスは、COM インターフェイスです。

次の例では、C3136 が生成されます。

```
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