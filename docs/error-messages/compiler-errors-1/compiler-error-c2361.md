---
title: コンパイラ エラー C2361 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2361
dev_langs:
- C++
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d91ee8b004e2f485326378eb2e1611f217f745c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029794"
---
# <a name="compiler-error-c2361"></a>コンパイラ エラー C2361

'identifier' の初期化が 'default' ラベルでスキップされました

初期化`identifier`でスキップすることができます、`switch`ステートメント。 宣言がブロックで囲まれている場合を除き、初期化子と共に宣言ジャンプすることはできません。 (が終わるまで、変数がスコープ内ではブロック内で宣言されている場合を除き、`switch`ステートメントです)。

次の例では、C2361 が生成されます。

```
// C2361.cpp
void func( void ) {
   int x;
   switch (x) {
   case 0 :
      int i = 1;
      { int j = 1; }
   default :   // C2361 error
      int k = 1;
   }
}
```

考えられる解決方法:

```
// C2361b.cpp
// compile with: /c
void func( void ) {
   int x = 0;
   switch (x) {
   case 0 :
      { int j = 1; int i = 1;}
   default :
      int k = 1;
   }
}
```