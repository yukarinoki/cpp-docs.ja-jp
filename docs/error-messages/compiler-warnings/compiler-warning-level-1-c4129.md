---
title: コンパイラの警告 (レベル 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: dc4f4c4c1feeba543ce0baa71e1ee5dfd81fdcae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310957"
---
# <a name="compiler-warning-level-1-c4129"></a>コンパイラの警告 (レベル 1) C4129

'character' : unrecognized character escape sequence

`character`次の円記号 (\\) 文字または文字列の定数はない有効なエスケープ シーケンスとして認識します。 バック スラッシュは無視され、印刷されません。 円記号の後の文字が出力されます。

1 つの円記号を印刷するには、二重の円記号を指定 (\\\\)。

C++ 標準で 2.13.2 のセクションでは、エスケープ シーケンスについて説明します。

次の例では、C4129 が生成されます。

```
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```