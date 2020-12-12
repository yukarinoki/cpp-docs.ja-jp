---
description: 詳細については、「コンパイラエラー C2711」を参照してください。
title: コンパイラエラー C2711
ms.date: 11/04/2016
f1_keywords:
- C2711
helpviewer_keywords:
- C2711
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
ms.openlocfilehash: 19c55327b4d2726f679494bba1de188537f6e094
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320845"
---
# <a name="compiler-error-c2711"></a>コンパイラエラー C2711

' function ': この関数はマネージとしてコンパイルできません。 #pragma アンマネージドを使用することを検討してください

指示によっては、外側の関数の MSIL をコンパイラが生成できないようにします。

次の例では、C2711 が生成されます。

```cpp
// C2711.cpp
// compile with: /clr
// processor: x86
using namespace System;
value struct V {
   static const t = 10;
};

void bar() {
   V::t;
   __asm int 3   // C2711 inline asm can't be compiled managed
}
```
