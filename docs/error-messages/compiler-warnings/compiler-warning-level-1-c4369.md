---
title: コンパイラの警告 (レベル 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: b374b67fa3319be35490358d7664bcb45bc640db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207031"
---
# <a name="compiler-warning-level-1-c4369"></a>コンパイラの警告 (レベル 1) C4369

'enumerator' :  enumerator value 'value' cannot be represented as 'type', value is 'new_value'

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