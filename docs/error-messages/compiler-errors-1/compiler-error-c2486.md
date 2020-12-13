---
description: 詳細については、「コンパイラエラー C2486」を参照してください。
title: コンパイラ エラー C2486
ms.date: 11/04/2016
f1_keywords:
- C2486
helpviewer_keywords:
- C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
ms.openlocfilehash: c45e0bdb0f515743694fe372bea3afdb24e00177
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339359"
---
# <a name="compiler-error-c2486"></a>コンパイラ エラー C2486

' __LOCAL_SIZE ' は、' 生 ' 属性を持つ関数でのみ許可されています

インラインアセンブリ関数では、名前は、 `__LOCAL_SIZE` [生](../../cpp/naked-cpp.md) の属性を使用して宣言された関数用に予約されています。

次の例では、C2486 が生成されます。

```cpp
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
