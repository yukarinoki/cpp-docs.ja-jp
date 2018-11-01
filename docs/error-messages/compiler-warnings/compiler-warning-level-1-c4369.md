---
title: コンパイラの警告 (レベル 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: b374b67fa3319be35490358d7664bcb45bc640db
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623954"
---
# <a name="compiler-warning-level-1-c4369"></a>コンパイラの警告 (レベル 1) C4369

'列挙子': 列挙子の値 'value' を 'type' として表現できず、値は 'new_value'

列挙子を計算すると、指定した基になる型の最大値よりも大きい値を指定します。  これにより、オーバーフローが発生し、コンパイラが型の最小値を列挙子の値をラップします。

## <a name="example"></a>例

次の例では、C4369 が生成されます。

```
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```