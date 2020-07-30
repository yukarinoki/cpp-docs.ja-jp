---
title: '前置インクリメント演算子と前置デクリメント演算子: ++ および --'
ms.date: 11/04/2016
f1_keywords:
- --
- ++
helpviewer_keywords:
- increment operators [C++], syntax
- ++ operator [C++], prefix increment operators
- operators [C++], decrement
- -- operator [C++], prefix decrement operators [C++]
- operators [C++], increment
- decrement operators [C++], syntax
- decrement operators [C++]
ms.assetid: 45ea7fc7-f279-4be9-a216-1d9a0ef9eb7b
ms.openlocfilehash: 0b84360f41c665707a03ad453909c054ac741405
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231157"
---
# <a name="prefix-increment-and-decrement-operators--and---"></a>前置インクリメント演算子と前置デクリメント演算子: ++ および --

## <a name="syntax"></a>構文

```
++ unary-expression
-- unary-expression
```

## <a name="remarks"></a>解説

前置インクリメント演算子 () は、 **++** オペランドに1つを追加します。この増分値は、式の結果です。 オペランドは型ではなく左辺値である必要があり **`const`** ます。 結果は、オペランドと同じ型の左辺値です。

前置デクリメント演算子 ( **--** ) は前置インクリメント演算子に似ていますが、オペランドが1つ減少し、結果がこのデクリメントされた値になる点が異なります。

**Visual Studio 2017 バージョン15.3 以降**( [/std: c++ 17](../build/reference/std-specify-language-standard-version.md)で利用可能): インクリメント演算子またはデクリメント演算子のオペランドを型にすることはできません **`bool`** 。

前置および後置インクリメントおよびデクリメント演算子は、オペランドに影響します。 これらの主要な違いは、式の評価でインクリメントまたはデクリメントが発生する順序です。 (詳細については、「[後置インクリメント演算子とデクリメント演算子](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)」を参照してください)。プレフィックス形式では、値が式の評価で使用される前にインクリメントまたはデクリメントが行われるため、式の値はオペランドの値とは異なります。 後置形式では、値が式評価で使用された後にインクリメントまたはデクリメントが発生するため、式の値はオペランドの値と同じになります。 たとえば、次のプログラムでは、"`++i = 6`" と出力されます。

```cpp
// expre_Increment_and_Decrement_Operators.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main() {
   int i = 5;
   cout << "++i = " << ++i << endl;
}
```

整数または浮動小数点型のオペランドは、整数値 1 ずつインクリメントまたはデクリメントされます。 結果の型は、オペランドの型と同じです。 ポインター型のオペランドは、アドレス指定するオブジェクトのサイズだけインクリメントまたはデクリメントされます。 インクリメントされたポインターは、次のオブジェクトを指します。デクリメントされたポインターは、前のオブジェクトを指します。

インクリメント演算子とデクリメント演算子には副作用があるため、[プリプロセッサマクロ](../preprocessor/macros-c-cpp.md)でインクリメントまたはデクリメント演算子を含む式を使用すると、望ましくない結果が生じる可能性があります。 次の例を考えてみましょう。

```cpp
// expre_Increment_and_Decrement_Operators2.cpp
#define max(a,b) ((a)<(b))?(b):(a)

int main()
{
   int i = 0, j = 0, k;
   k = max( ++i, j );
}
```

マクロは次のように展開されます。

```cpp
k = ((++i)<(j))?(j):(++i);
```

`i` が `j` 以上であるか、`j` より 1 少ない場合、2 回インクリメントされます。

> [!NOTE]
> C++ のインライン関数は、ここで説明したような副作用をなくし、言語でより完全な型チェックを実行できるため、多くの場合、マクロよりも適しています。

## <a name="see-also"></a>関連項目

[単項演算子を含む式](../cpp/expressions-with-unary-operators.md)<br/>
[C++ の演算子、優先順位と結合規則](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[前置インクリメント演算子と前置デクリメント演算子](../c-language/prefix-increment-and-decrement-operators.md)
