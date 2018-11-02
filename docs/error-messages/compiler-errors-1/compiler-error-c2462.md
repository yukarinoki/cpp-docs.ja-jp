---
title: コンパイラ エラー C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: 0b342f8b878c48a77336fab4921cf4a668e248ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607052"
---
# <a name="compiler-error-c2462"></a>コンパイラ エラー C2462

'identifier': ' new' 式で型を定義することはできません

オペランド フィールドの型を定義することはできません、`new`演算子。 別のステートメントでは、型定義を配置します。

次の例では、C2462 が生成されます。

```
// C2462.cpp
int main() {
   new struct S { int i; };   // C2462
}
```