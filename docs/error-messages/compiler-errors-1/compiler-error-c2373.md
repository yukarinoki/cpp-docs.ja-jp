---
title: コンパイラ エラー C2373
ms.date: 11/04/2016
f1_keywords:
- C2373
helpviewer_keywords:
- C2373
ms.assetid: 7a08bf0b-852d-48be-ba75-70df9f4b5951
ms.openlocfilehash: 967bdec10e0e1c04083770d52da930837d8eeb7e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570366"
---
# <a name="compiler-error-c2373"></a>コンパイラ エラー C2373

'identifier': 再定義されています。異なる型修飾子です

識別子は、異なる型修飾子で既に定義されています。

次の例では C2373 が生成されます。

```
// C2373.h
void __clrcall func( void );
const int i = 20;
```

この場合、次のようになります。

```
// C2373.cpp
// compile with: /c
#include "C2373.h"
extern void __cdecl func( void );   // C2373
extern void __clrcall func( void );   // OK

extern int i;   // C2373
extern const int i;   // OK
```