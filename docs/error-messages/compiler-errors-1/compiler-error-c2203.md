---
title: コンパイラ エラー C2203
ms.date: 11/04/2016
f1_keywords:
- C2203
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
ms.openlocfilehash: 848fdad460402238f4957344dd49bd9128352b4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383270"
---
# <a name="compiler-error-c2203"></a>コンパイラ エラー C2203

削除演算子は配列の境界を指定できません

**/Za** (ANSI) のオプション、`delete`演算子には、配列全体ですがない部分または配列の特定のメンバーを削除できます。

次の例では、C2203 が生成されます。

```
// C2203.cpp
// compile with: /Za
int main() {
   int *ar = new int[10];
   delete [4] ar;   // C2203
   // try the following line instead
   // delete [] ar;
}
```