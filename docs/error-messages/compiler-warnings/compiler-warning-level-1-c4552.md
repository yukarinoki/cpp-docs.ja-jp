---
title: コンパイラの警告 (レベル 1) C4552
ms.date: 11/04/2016
f1_keywords:
- C4552
helpviewer_keywords:
- C4552
ms.assetid: ebbbb5ee-1c19-45bd-b386-41a19630fc76
ms.openlocfilehash: 8435abc60a7ba93800858b22cfd4c5e1778f8587
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186115"
---
# <a name="compiler-warning-level-1-c4552"></a>コンパイラの警告 (レベル 1) C4552

' operator ': 演算子は無効です。副作用のある演算子が必要です

式ステートメントに、式の先頭として副作用のない演算子が含まれている場合は、間違いであると思います。

この警告をオーバーライドするには、式をかっこで囲みます。

次の例では、C4552 が生成されます。

```cpp
// C4552.cpp
// compile with: /W1
int main() {
   int i, j;
   i + j;   // C4552
   // try the following line instead
   // (i + j);
}
```
