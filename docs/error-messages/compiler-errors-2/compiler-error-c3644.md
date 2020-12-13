---
description: 詳細については、「コンパイラエラー C3644」を参照してください。
title: コンパイラ エラー C3644
ms.date: 11/04/2016
f1_keywords:
- C3644
helpviewer_keywords:
- C3644
ms.assetid: 2e3f6c41-3ec5-4a01-82bc-f11b61ebe68e
ms.openlocfilehash: e08471583dea096481115f3d710a1854ef00baf9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340282"
---
# <a name="compiler-error-c3644"></a>コンパイラ エラー C3644

' function ': マネージドコードを生成するために関数をコンパイルすることはできません

関数にいくつかのキーワードが存在すると、関数がネイティブにコンパイルされます。

次の例では、C3644 が生成されます。

```cpp
// C3644.cpp
// compile with: /clr
// processor: x86

void __clrcall Func2(int i) {
   __asm {}   // C3644
}
```
