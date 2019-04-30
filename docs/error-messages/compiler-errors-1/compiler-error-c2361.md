---
title: コンパイラ エラー C2361
ms.date: 11/04/2016
f1_keywords:
- C2361
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
ms.openlocfilehash: ca03a42cbf746a1ef32d9c79c23de637f05b56fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62364364"
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