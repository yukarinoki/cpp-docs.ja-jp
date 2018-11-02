---
title: コンパイラ エラー C2748
ms.date: 11/04/2016
f1_keywords:
- C2748
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
ms.openlocfilehash: a85ee151d9a4d62cc4b95248d669ff924365a95a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655638"
---
# <a name="compiler-error-c2748"></a>コンパイラ エラー C2748

マネージド配列または WinRT 配列を作成するには、配列のサイズまたは配列の初期化子を指定する必要があります。

マネージド配列または WinRT 配列の形式が正しくありません。 詳細については、「 [配列](../../windows/arrays-cpp-component-extensions.md)」を参照してください。

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