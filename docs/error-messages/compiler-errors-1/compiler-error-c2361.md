---
description: 詳細については、「コンパイラエラー C2361」を参照してください。
title: コンパイラ エラー C2361
ms.date: 11/04/2016
f1_keywords:
- C2361
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
ms.openlocfilehash: 53ca69daf347d23bb27e214556a74c70c1e53725
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328320"
---
# <a name="compiler-error-c2361"></a>コンパイラ エラー C2361

' identifier ' の初期化が ' default ' ラベルによってスキップされました

ステートメントでは、の初期化を `identifier` スキップでき **`switch`** ます。 宣言がブロックで囲まれている場合を除き、初期化子を使用して宣言をスキップすることはできません。 (ブロック内で宣言されていない限り、変数はステートメントの最後までスコープ内に **`switch`** あります)。

次の例では、C2361 が生成されます。

```cpp
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

考えられる解決策:

```cpp
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
