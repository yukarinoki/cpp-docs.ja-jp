---
description: 詳細については、「コンパイラエラー C2373」を参照してください。
title: コンパイラ エラー C2373
ms.date: 11/04/2016
f1_keywords:
- C2373
helpviewer_keywords:
- C2373
ms.assetid: 7a08bf0b-852d-48be-ba75-70df9f4b5951
ms.openlocfilehash: 53646a0440576b1d7a5c185102e54af9f9a83e8f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174833"
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

```cpp
// C2373.cpp
// compile with: /c
#include "C2373.h"
extern void __cdecl func( void );   // C2373
extern void __clrcall func( void );   // OK

extern int i;   // C2373
extern const int i;   // OK
```
