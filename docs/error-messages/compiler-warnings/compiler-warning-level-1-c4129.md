---
description: '詳細情報: コンパイラの警告 (レベル 1) C4129'
title: コンパイラの警告 (レベル 1) C4129
ms.date: 11/04/2016
f1_keywords:
- C4129
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
ms.openlocfilehash: 27ae487016a5d9a60a95e4715261ec5ba9171db4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155281"
---
# <a name="compiler-warning-level-1-c4129"></a>コンパイラの警告 (レベル 1) C4129

' character ': 認識できない文字エスケープシーケンスです。

`character` \\ 文字または文字列定数内の次の円記号 () は、有効なエスケープシーケンスとして認識されません。 円記号は無視され、印刷されません。 円記号の後に続く文字が出力されます。

1つの円記号を印刷するには、二重の円記号 () を指定し \\ \\ ます。

セクション2.13.2 の C++ 標準では、エスケープシーケンスについて説明しています。

次の例では、C4129 が生成されます。

```cpp
// C4129.cpp
// compile with: /W1
int main() {
   char array1[] = "\/709";   // C4129
   char array2[] = "\n709";   // OK
}
```
