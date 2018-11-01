---
title: コンパイラ エラー C2767
ms.date: 11/04/2016
f1_keywords:
- C2767
helpviewer_keywords:
- C2767
ms.assetid: e8f84178-a160-4d71-a236-07e4fcc11e96
ms.openlocfilehash: 6c13610b6fd7aae4b4232b836a0307867bd591d7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550151"
---
# <a name="compiler-error-c2767"></a>コンパイラ エラー C2767

マネージ型または WinRTarray ディメンションの不一致: M が設定されます - N 個の引数が必要です

マネージド配列または WinRT 配列の宣言の形式が正しくありません。 詳細については、「 [配列](../../windows/arrays-cpp-component-extensions.md)」を参照してください。

次の例では、C2767 を生成し、その修正方法を示しています。

```
// C2767.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>(2,3); // C2767
   array<int> ^p2 = new array<int>(2);   // OK
}
```