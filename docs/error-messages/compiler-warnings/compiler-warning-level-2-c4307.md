---
title: コンパイラの警告 (レベル 2) C4307
ms.date: 11/04/2016
f1_keywords:
- C4307
helpviewer_keywords:
- C4307
ms.assetid: 7cca11e9-be61-49e4-8b15-88b84f0cbf07
ms.openlocfilehash: e9ad30f60260893130beed921aab811c894868cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402503"
---
# <a name="compiler-warning-level-2-c4307"></a>コンパイラの警告 (レベル 2) C4307

'operator': 定数整数のオーバーフロー

演算子は、それに割り当てられた領域をオーバーフローする整数の定数に評価される式で使用されます。 定数のより大きい型を使用する必要があります。 A **int を署名**よりも小さい値を保持、`unsigned int`ため、 **int を署名**1 ビットを使用して、記号を表します。

次の例では、C4307 が生成されます。

```
// C4307.cpp
// compile with: /W2
int i = 2000000000 + 2000000000;   // C4307
int j = (unsigned)2000000000 + 2000000000;   // OK

int main()
{
}
```