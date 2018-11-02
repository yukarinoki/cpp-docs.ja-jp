---
title: コンパイラ エラー C3149
ms.date: 11/04/2016
f1_keywords:
- C3149
helpviewer_keywords:
- C3149
ms.assetid: cf6e2616-2f06-46da-8a8a-d449cb481c51
ms.openlocfilehash: 8238dcec821256dad8101cd7ad59b2d85882c218
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622873"
---
# <a name="compiler-error-c3149"></a>コンパイラ エラー C3149

'type': 最上位レベルの 'char' なしに、この型をここで使用できません

宣言が正しく指定されていません。

たとえば、可能性がありますグローバル スコープの CLR 型を定義して、定義の一部として、型の変数を作成しようとしました。 CLR 型のグローバル変数は使用できないため、コンパイラは C3149 を生成します。

このエラーを解決するには、関数または型定義内の CLR 型の変数を宣言します。

次の例では、C3149 が生成されます。

```
// C3149.cpp
// compile with: /clr
using namespace System;
int main() {
   // declare an array of value types
   array< Int32 ^> IntArray;   // C3149
   array< Int32>^ IntArray2;   // OK
}
```

次の例では、C3149 が生成されます。

```
// C3149b.cpp
// compile with: /clr /c
delegate int MyDelegate(const int, int);
void Test1(MyDelegate m) {}   // C3149
void Test2(MyDelegate ^ m) {}   // OK
```
