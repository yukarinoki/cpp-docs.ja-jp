---
title: コンパイラ エラー C2711
ms.date: 11/04/2016
f1_keywords:
- C2711
helpviewer_keywords:
- C2711
ms.assetid: 9df9f808-7419-4e63-abdd-e6538ff0871f
ms.openlocfilehash: 568128d6199d16380b6a540173eded25f5588d23
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160940"
---
# <a name="compiler-error-c2711"></a>コンパイラ エラー C2711

'function': この関数にすることはできませんマネージとしてコンパイル #pragma アンマネージドを使用を検討してください

一部の命令すると、コンパイラが、外側の関数の MSIL を生成できなくなります。

次の例では、C2711 が生成されます。

```
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