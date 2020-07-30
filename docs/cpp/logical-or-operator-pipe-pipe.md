---
title: '論理 OR 演算子:  &#124;&#124;'
description: C++ 標準言語の論理 OR 演算子の構文で、を使用します。
ms.date: 07/23/2020
f1_keywords:
- '||'
- or_cpp
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
ms.openlocfilehash: 1845aef59f88d5dd044cefedd21cb618e1102e13
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225996"
---
# <a name="logical-or-operator-124124"></a>論理 OR 演算子:  &#124;&#124;

## <a name="syntax"></a>構文

> *論理 or 式* **`||`***論理 and 式*

## <a name="remarks"></a>解説

論理 OR 演算子 () は、 **`||`** いずれかまたは両方のオペランドがである場合はブール値を返し、 **`true`** それ以外の場合は **`true`** を返し **`false`** ます。 オペランドは評価前に型に暗黙的に変換され、 **`bool`** 結果は型になり **`bool`** ます。 論理 OR の結合規則は左から右です。

論理 OR 演算子のオペランドは、同じ型である必要はありませんが、ブール型、整数型、またはポインター型である必要があります。 オペランドは一般に関係式または等価式です。

最初のオペランドが完全に評価され、すべての副作用が完了した後で、論理 OR 式の評価が続行されます。

2番目のオペランドは、最初のオペランドがと評価された場合にのみ評価され **`false`** ます。これは、論理 OR 式がの場合、評価は必要ないためです **`true`** 。 これは、*ショートサーキット*評価と呼ばれます。

```cpp
printf( "%d" , (x == w || x == y || x == z) );
```

上の例で、 `x` が、、またはのいずれかに等しい場合、 `w` `y` `z` 関数の2番目の引数は `printf` とし **`true`** て評価され、その後整数に上位変換され、値1が出力されます。 それ以外の場合は、と評価され、 **`false`** 値0が出力されます。 条件の1つがに評価されるとすぐに **`true`** 、評価が停止します。

## <a name="operator-keyword-for-124124"></a> &#124;&#124; の Operator キーワード

C++ **`or`** では、の代替スペルとしてを指定し **`||`** ます。 C では、代替のスペルは、ヘッダーにマクロとして指定され \<iso646.h> ます。 C++ では、代替のスペルはキーワードです。\<iso646.h>または C++ と同等のの使用 \<ciso646> は非推奨とされます。 Microsoft C++ では、 [`/permissive-`](../build/reference/permissive-standards-conformance.md) またはコンパイラオプションを使用して、 [`/Za`](../build/reference/za-ze-disable-language-extensions.md) 別のスペルチェックを有効にする必要があります。

## <a name="example"></a>例

```cpp
// expre_Logical_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate logical OR
#include <iostream>
using namespace std;
int main() {
   int a = 5, b = 10, c = 15;
   cout  << boolalpha
         << "The true expression "
         << "a < b || b > c yields "
         << (a < b || b > c) << endl
         << "The false expression "
         << "a > b || b > c yields "
         << (a > b || b > c) << endl;
}
```

## <a name="see-also"></a>関連項目

[C++ の組み込み演算子、優先順位、および結合規則](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[C 論理演算子](../c-language/c-logical-operators.md)
