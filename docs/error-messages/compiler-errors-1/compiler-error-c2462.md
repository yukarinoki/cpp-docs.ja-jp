---
title: コンパイラ エラー C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: 8db79bf9813d9701b45d9a0427f68cfbecc3eba4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214673"
---
# <a name="compiler-error-c2462"></a>コンパイラ エラー C2462

' identifier ': ' new ' 式で型を定義することはできません

演算子のオペランドフィールドに型を定義することはできません **`new`** 。 型定義を別のステートメントに配置します。

次の例では、C2462 が生成されます。

```cpp
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```
