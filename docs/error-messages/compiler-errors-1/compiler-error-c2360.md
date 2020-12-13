---
description: 詳細については、「コンパイラエラー C2360」を参照してください。
title: コンパイラ エラー C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: c71a82816edfacede51a5774fec5e90560d964a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136462"
---
# <a name="compiler-error-c2360"></a>コンパイラ エラー C2360

' identifier ' の初期化は ' case ' ラベルによってスキップされます

ステートメントでは、の初期化を `identifier` スキップでき **`switch`** ます。 宣言がブロックで囲まれている場合を除き、初期化子を使用して宣言をスキップすることはできません。 (ブロック内で宣言されていない限り、変数はステートメントの最後までスコープ内に **`switch`** あります)。

次の例では、C2360 が生成されます。

```cpp
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

考えられる解決策:

```cpp
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```
