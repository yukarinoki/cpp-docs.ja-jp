---
description: 詳細については、「コンパイラエラー C2462」を参照してください。
title: コンパイラ エラー C2462
ms.date: 11/04/2016
f1_keywords:
- C2462
helpviewer_keywords:
- C2462
ms.assetid: a8601bf8-f5ce-41de-9117-e2632bd4996b
ms.openlocfilehash: f85d8f2e38c38043765b29b6e766c0cbd4fef1fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341816"
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
