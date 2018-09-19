---
title: コンパイラ エラー C3136 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 0439aa157a683065ccf7fff5b5f9d6d4d85e2f12
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054221"
---
# <a name="compiler-error-c3136"></a>コンパイラ エラー C3136

'interface': COM インターフェイスは、別の COM インターフェイスからのみ継承できます、'interface' は COM インターフェイスはありません。

適用されているインターフェイス、[インターフェイス属性](../../windows/interface-attributes.md)COM インターフェイスではないインターフェイスから継承します。 COM インターフェイスが最終的に継承`IUnknown`します。 インターフェイス属性に続く任意のインターフェイスは、COM インターフェイスです。

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