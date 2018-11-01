---
title: コンパイラの警告 (レベル 2) C4309
ms.date: 11/04/2016
f1_keywords:
- C4309
helpviewer_keywords:
- C4309
ms.assetid: cb3f41ef-fd8a-4def-baa1-924e751fca68
ms.openlocfilehash: 41184571dc07213c796c039170966a0c7150bd45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516143"
---
# <a name="compiler-warning-level-2-c4309"></a>コンパイラの警告 (レベル 2) C4309

'conversion': 定数値の切り捨て

型変換によって、それに割り当てられた領域を超過する定数。 定数のより大きい型を使用する必要があります。

次の例では、C4309 が生成されます。

```
// C4309.cpp
// compile with: /W2
int main()
{
   char c = 128;   // C4309
}
```