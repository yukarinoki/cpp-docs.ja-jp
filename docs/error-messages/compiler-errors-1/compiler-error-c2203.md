---
title: コンパイラ エラー C2203
ms.date: 11/04/2016
f1_keywords:
- C2203
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
ms.openlocfilehash: 4a078cd4c64bbb8d301aa3e4817272d23e3acbb4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216311"
---
# <a name="compiler-error-c2203"></a>コンパイラ エラー C2203

delete 演算子で配列の境界を指定することはできません

**/Za** (ANSI) オプションを使用すると、演算子は配列 **`delete`** 全体を削除できますが、配列の一部または特定のメンバーを削除することはできません。

次の例では、C2203 が生成されます。

```cpp
// C2203.cpp
// compile with: /Za
int main() {
   int *ar = new int[10];
   delete [4] ar;   // C2203
   // try the following line instead
   // delete [] ar;
}
```
