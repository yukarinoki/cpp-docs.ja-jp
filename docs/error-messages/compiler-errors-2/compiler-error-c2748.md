---
description: 詳細については、「コンパイラエラー C2748」を参照してください。
title: コンパイラエラー C2748
ms.date: 11/04/2016
f1_keywords:
- C2748
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
ms.openlocfilehash: 64720391906777ffd5f36c53e6f7ce27940426fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123020"
---
# <a name="compiler-error-c2748"></a>コンパイラエラー C2748

マネージド配列または WinRT 配列を作成するには、配列のサイズまたは配列の初期化子を指定する必要があります。

マネージド配列または WinRT 配列の形式が正しくありません。 詳細については、「 [配列](../../extensions/arrays-cpp-component-extensions.md)」を参照してください。

次の例では C2748 を生成し、その修正方法を示しています。

```cpp
// C2748.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>();   // C2748
   // try the following line instead
   array<int> ^p2 = new array<int>(2);
}
```
