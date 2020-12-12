---
description: 詳細については、「コンパイラエラー C2739」を参照してください。
title: コンパイラエラー C2739
ms.date: 11/04/2016
f1_keywords:
- C2739
helpviewer_keywords:
- C2739
ms.assetid: 5b63e435-7631-43d7-805e-f2adefb7e517
ms.openlocfilehash: 2a65f552eeb8a0b475b5559aaa3f1ab6b0da0e25
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123085"
---
# <a name="compiler-error-c2739"></a>コンパイラエラー C2739

'number': 明示的なマネージドまたは WinRT 配列の次元は 1 から 32 の間でなければなりません

配列の次元が 1 ～ 32 ではありませんでした。

次の例では、C2739 を生成し、その修正方法を示しています。

```cpp
// C2739.cpp
// compile with: /clr
int main() {
   array<int, -1>^a;   // C2739
   // try the following line instead
   // array<int, 2>^a;
}
```
