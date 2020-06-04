---
title: コンパイラの警告 (レベル 2) C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: f6e06acaf43708d6c0da6d67531b6c4b9f202971
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161881"
---
# <a name="compiler-warning-level-2-c4307"></a>コンパイラの警告 (レベル 2) C4307

' operator ': 整数定数がオーバーフローしています。

演算子は、割り当てられた領域を整数定数でオーバーフローする式で使用されます。 定数には、より大きな型を使用することが必要になる場合があります。 符号**付き整数は**、符号を表すために1ビット**を使用する**ため、`unsigned int` よりも小さい値を保持します。

次の例では、C4307 が生成されます。

```cpp
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```
