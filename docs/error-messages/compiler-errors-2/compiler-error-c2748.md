---
title: コンパイラ エラー C2748
ms.date: 11/04/2016
f1_keywords:
- C2748
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
ms.openlocfilehash: 251492b736ba3325ed263a9a8754fc8fa480c664
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58771878"
---
# <a name="compiler-error-c2748"></a>コンパイラ エラー C2748

マネージド配列または WinRT 配列を作成するには、配列のサイズまたは配列の初期化子を指定する必要があります。

マネージド配列または WinRT 配列の形式が正しくありません。 詳細については、「 [配列](../../extensions/arrays-cpp-component-extensions.md)」を参照してください。

次の例では C2748 を生成し、その修正方法を示しています。

```
// C2748.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>();   // C2748
   // try the following line instead
   array<int> ^p2 = new array<int>(2);
}
```