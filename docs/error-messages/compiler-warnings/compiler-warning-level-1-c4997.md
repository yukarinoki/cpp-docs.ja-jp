---
title: コンパイラの警告 (レベル 1) C4997 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4997
dev_langs:
- C++
helpviewer_keywords:
- C4997
ms.assetid: d39678fd-0c1a-4104-8a45-9e3f20de0407
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab199f4dd884c1a2371704a836546bdb43aabed6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026700"
---
# <a name="compiler-warning-level-1-c4997"></a>コンパイラの警告 (レベル 1) C4997

'class': コクラスは COM インターフェイスまたは擬似インターフェイスを実装しません

[coclass](../../windows/coclass.md) 属性でマークされているクラスがインターフェイスを実装しませんでした。

次の例では C4997 が生成されます。

```
// C4997.cpp
// compile with: /WX
// to resolve this C4997, uncomment all code
#include <objbase.h>

[ object ]
__interface I {
   HRESULT func();
};

[ coclass ]
struct C /*: I*/ {
   /*
   HRESULT func() {
      return S_OK;
   }
   */
};   // C4997
```