---
title: コンパイラ エラー C2486
ms.date: 11/04/2016
f1_keywords:
- C2486
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
ms.openlocfilehash: 8d745c03530f331da83b45c765a2cb4bb7d76d8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555654"
---
# <a name="compiler-error-c2486"></a>コンパイラ エラー C2486

'_ _Local_size' は 'naked' 属性を持つ関数でのみ使用できます。

インライン アセンブリの関数では名前で`__LOCAL_SIZE`で宣言されている関数に予約されていますが、 [naked](../../cpp/naked-cpp.md)属性。

次の例では、C2486 が生成されます。

```
// C2486.cpp
// processor: x86
void __declspec(naked) f1() {
   __asm {
      mov   eax,   __LOCAL_SIZE
   }
}
void f2() {
   __asm {
      mov   eax,   __LOCAL_SIZE   // C2486
   }
}
```