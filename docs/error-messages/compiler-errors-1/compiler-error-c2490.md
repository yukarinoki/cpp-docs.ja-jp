---
title: コンパイラ エラー C2490
ms.date: 11/04/2016
f1_keywords:
- C2490
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
ms.openlocfilehash: 9e06883d0e8b6103eb44d086d3872d86c50a58b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452092"
---
# <a name="compiler-error-c2490"></a>コンパイラ エラー C2490

' keyword' は 'naked' 属性を持つ関数では使用できません。

として定義されている関数[naked](../../cpp/naked-cpp.md)構造化例外処理を使用することはできません。

次の例では、C2490 が生成されます。

```
// C2490.cpp
// processor: x86
__declspec( naked ) int func() {
   __try{}   // C2490, structured exception handling
}
```