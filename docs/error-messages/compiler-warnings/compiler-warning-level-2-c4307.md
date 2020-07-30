---
title: コンパイラの警告 (レベル 2) C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: d0179dc5f5cb9367ee83a7f40f8b9ceb368474fa
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218131"
---
# <a name="compiler-warning-level-2-c4307"></a>コンパイラの警告 (レベル 2) C4307

' operator ': 整数定数がオーバーフローしています。

演算子は、割り当てられた領域を整数定数でオーバーフローする式で使用されます。 定数には、より大きな型を使用することが必要になる場合があります。 は **`signed int`** **`unsigned int`** **`signed int`** 符号を表すために1ビットを使用するため、はより小さい値を保持します。

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
