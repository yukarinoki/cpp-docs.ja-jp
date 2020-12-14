---
description: '詳細情報: コンパイラの警告 (レベル 1) C4739'
title: コンパイラの警告 (レベル 1) C4739
ms.date: 11/04/2016
f1_keywords:
- C4739
helpviewer_keywords:
- C4739
ms.assetid: 600873b3-7c85-4cd4-944e-cd8e01bfcbb0
ms.openlocfilehash: 03473c8bb5434e8ee05778f40c2cf773de1b64da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228548"
---
# <a name="compiler-warning-level-1-c4739"></a>コンパイラの警告 (レベル 1) C4739

変数 'var' への参照はそのストレージ領域を超えています

変数に代入された値が、変数のサイズを超えています。 変数のメモリ位置を超えるメモリが書き込まれるため、データ損失が発生する可能性があります。

この警告を解決するには、その値を格納できるサイズの変数にのみ値を割り当てます。

次の例では C4739 が生成されます。

```cpp
// C4739.cpp
// compile with: /RTCs /Zi /W1 /c
char *pc;
int main() {
   char c;
   *(int *)&c = 1;   // C4739

   // OK
   *(char *)&c = 1;
}
```
