---
description: '詳細情報: コンパイラの警告 (レベル 1) C4369'
title: コンパイラの警告 (レベル 1) C4369
ms.date: 11/04/2016
f1_keywords:
- C4369
helpviewer_keywords:
- C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
ms.openlocfilehash: 97f7882438124e8788559ec1453bd84d3ec371d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339970"
---
# <a name="compiler-warning-level-1-c4369"></a>コンパイラの警告 (レベル 1) C4369

' enumerator ': 列挙子の値 ' value ' を ' type ' として表すことはできません。値は ' new_value ' です

列挙子が、指定された基になる型の最大値を超えていることが計算されました。  これによりオーバーフローが発生し、コンパイラが列挙子の値をその型の可能な最小値にラップしました。

## <a name="example"></a>例

次の例では、C4369 が生成されます。

```cpp
// C4369.cpp
// compile with: /W1
int main() {
   enum Color: char { red = 0x7e, green, blue };   // C4369
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK
}
```
